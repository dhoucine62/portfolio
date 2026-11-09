<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';

interface GitHubProfile {
  public_repos: number;
  followers: number;
}

interface GitHubRepository {
  stargazers_count: number;
  fork: boolean;
}

const username = 'dhoucine62';
const profileUrl = `https://github.com/${username}`;
const status = ref<'loading' | 'ready' | 'error'>('loading');
const stats = ref<{ repositories: number; stars: number; followers: number }>();
let controller: AbortController | undefined;

async function fetchGitHub<T>(path: string, signal: AbortSignal): Promise<T> {
  const response = await fetch(`https://api.github.com/users/${username}${path}`, {
    headers: { Accept: 'application/vnd.github+json' },
    signal,
  });
  if (!response.ok) throw new Error(`GitHub: ${response.status}`);
  return response.json() as Promise<T>;
}

async function loadStats() {
  controller?.abort();
  const request = new AbortController();
  controller = request;
  status.value = 'loading';
  const timeout = window.setTimeout(() => request.abort(), 10000);

  try {
    const [profile, repositories] = await Promise.all([
      fetchGitHub<GitHubProfile>('', request.signal),
      fetchGitHub<GitHubRepository[]>('/repos?per_page=100&page=1', request.signal),
    ]);
    if (!Number.isInteger(profile.public_repos) || !Number.isInteger(profile.followers) || !Array.isArray(repositories)) {
      throw new Error('Invalid GitHub response');
    }

    // Include every page so the star count stays correct beyond 100 repositories.
    for (let page = 2; page <= Math.ceil(profile.public_repos / 100); page++) {
      const nextPage = await fetchGitHub<GitHubRepository[]>(`/repos?per_page=100&page=${page}`, request.signal);
      if (!Array.isArray(nextPage)) throw new Error('Invalid GitHub response');
      repositories.push(...nextPage);
    }

    if (controller !== request) return;
    stats.value = {
      repositories: profile.public_repos,
      stars: repositories.reduce((total, repo) => total + (!repo.fork && Number.isInteger(repo.stargazers_count) ? repo.stargazers_count : 0), 0),
      followers: profile.followers,
    };
    status.value = 'ready';
  } catch {
    if (controller === request) status.value = 'error';
  } finally {
    window.clearTimeout(timeout);
  }
}

onMounted(loadStats);
onUnmounted(() => {
  controller?.abort();
  controller = undefined;
});
</script>

<template>
  <aside class="github-block" aria-labelledby="github-title">
    <div class="github-heading">
      <div>
        <p class="project-meta">Mon code sur GitHub</p>
        <h3 id="github-title"><a :href="profileUrl" target="_blank" rel="noopener noreferrer">@{{ username }} <span aria-hidden="true">↗</span></a></h3>
      </div>
      <a class="text-action github-profile-link" :href="profileUrl" target="_blank" rel="noopener noreferrer">Voir mon profil <span aria-hidden="true">↗</span></a>
    </div>
    <div class="github-stats-content" aria-live="polite" :aria-busy="status === 'loading'">
      <dl v-if="status === 'ready' && stats" class="github-stats">
        <div><dt>Dépôts publics</dt><dd>{{ stats.repositories.toLocaleString('fr-FR') }}</dd></div>
        <div><dt>Étoiles reçues</dt><dd>{{ stats.stars.toLocaleString('fr-FR') }}</dd></div>
        <div><dt>Abonnés</dt><dd>{{ stats.followers.toLocaleString('fr-FR') }}</dd></div>
      </dl>
      <p v-else-if="status === 'loading'" class="github-message">Chargement des statistiques…</p>
      <p v-else class="github-message">Les statistiques sont indisponibles pour le moment. <button @click="loadStats">Réessayer</button></p>
      <p v-if="status === 'ready'" class="github-stats-note">Statistiques publiques, actualisées à l’ouverture de la page.</p>
    </div>
  </aside>
</template>
