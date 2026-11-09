<script setup lang="ts">
import GithubStats from '@/component/GithubStats.vue';

const baseUrl = import.meta.env.BASE_URL;
</script>

<template>
  <section
    id="projets"
    class="projects-section section-shell"
    tabindex="-1"
    aria-labelledby="projects-title"
  >
    <div class="section-heading">
      <p class="eyebrow">03 / Projets</p>
    </div>
    <div class="projects-heading">
      <h2 id="projects-title">Ce que <span>je fais.</span></h2>
    </div>
    <article class="project-card">
      <a
        class="project-visual project-screenshot"
        href="https://www.curseforge.com/minecraft/mc-mods/tdwcm"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Découvrir THE Doctor Who Client Mod sur CurseForge"
      >
        <img
          :src="`${baseUrl}projects/tdwcm.png`"
          alt="Deux TARDIS dans Minecraft, dont un ouvert sur son intérieur."
          width="1920"
          height="1017"
          loading="lazy"
        />
        <span class="project-platform">CurseForge <span aria-hidden="true">↗</span></span>
      </a>
      <div class="project-info">
        <p class="project-meta">Mod Minecraft · Projet collectif</p>
        <h3>THE Doctor Who Client Mod</h3>
        <p>
          Un mod Minecraft autour de Doctor Who : pilotage du TARDIS,
          console interactive et exploration. Un projet collectif publié
          sur CurseForge.
        </p>
        <ul class="tech-tags" aria-label="À propos du projet">
          <li>Java</li>
          <li>Minecraft</li>
          <li>NeoForge</li>
          <li>Modding</li>
        </ul>
        <a
          class="text-action"
          href="https://www.curseforge.com/minecraft/mc-mods/tdwcm"
          target="_blank"
          rel="noopener noreferrer"
        >
          Voir sur CurseForge <span aria-hidden="true">↗</span>
        </a>
      </div>
    </article>
    <article class="project-card">
      <a
        class="project-visual project-screenshot"
        href="https://r0-m-1.itch.io/pyrotechclick"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Découvrir PyrotechClick sur itch.io"
      >
        <img
          :src="`${baseUrl}projects/pyrotechclick.png`"
          alt="Écran des commandes de PyrotechClick : déplacements, tirs et interactions à la souris."
          width="794"
          height="446"
          loading="lazy"
        />
        <span class="project-platform">itch.io <span aria-hidden="true">↗</span></span>
      </a>
      <div class="project-info">
        <p class="project-meta">Jeu vidéo · Code Game Jam 2026</p>
        <h3>PyrotechClick</h3>
        <p>
          Un jeu d’action en 2D réalisé avec Godot pour la Code Game Jam 2026.
          Le jeu est disponible en téléchargement sur itch.io.
        </p>
        <ul class="tech-tags" aria-label="À propos du projet">
          <li>Godot</li>
          <li>2D</li>
          <li>Game jam</li>
        </ul>
        <a
          class="text-action"
          href="https://r0-m-1.itch.io/pyrotechclick"
          target="_blank"
          rel="noopener noreferrer"
        >
          Voir sur itch.io <span aria-hidden="true">↗</span>
        </a>
      </div>
    </article>
    <article class="project-card">
      <a
        class="project-visual"
        href="#accueil"
        aria-label="Revoir l’accueil de mon portfolio"
      >
        <div class="project-preview" aria-hidden="true">
          <span class="preview-top">hd.<span>Mon portfolio</span></span>
          <span class="preview-title">HOUCINE<br /><span>DRIFI.</span></span>
          <span class="preview-bottom">Étudiant en informatique <span>↗</span></span>
        </div>
      </a>
      <div class="project-info">
        <p class="project-meta">Projet personnel</p>
        <h3>Ce portfolio</h3>
        <p>
          Je l’ai créé pour me présenter et rassembler mes projets.
          Il me sert aussi à pratiquer Vue et TypeScript, et à travailler
          la mise en page sur ordinateur comme sur mobile.
        </p>
        <ul class="tech-tags" aria-label="Technologies utilisées">
          <li>Vue 3</li>
          <li>TypeScript</li>
          <li>CSS</li>
        </ul>
        <a
          class="text-action"
          href="https://github.com/dhoucine62/portfolio"
          target="_blank"
          rel="noopener noreferrer"
        >
          Voir le code sur GitHub <span aria-hidden="true">↗</span>
        </a>
      </div>
    </article>
    <GithubStats />
  </section>
</template>
