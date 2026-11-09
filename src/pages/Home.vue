<script setup lang="ts">
import Competences from '@/component/Competences.vue';
import GithubStats from '@/component/GithubStats.vue';

const menu = [
  { label: 'À propos', href: '#a-propos', number: '01' },
  { label: 'Compétences', href: '#competences', number: '02' },
  { label: 'Projets', href: '#projets', number: '03' },
];
</script>

<template>
  <main>
    <section id="accueil" class="hero section-shell" tabindex="-1" aria-labelledby="hero-title">
      <div class="hero-layout">
        <div class="hero-copy">
          <p class="eyebrow">Bonjour, moi c’est</p>
          <h1 id="hero-title">HOUCINE<br /><span>DRIFI<span class="name-dot">.</span></span></h1>
          <p class="hero-role">Étudiant en informatique</p>
          <p class="hero-description">
            J’apprends à développer des sites web et des applications.
            Ici, je partage ce que je fais et ce que j’apprends en chemin.
          </p>
          <a class="action action-red" href="#projets">Voir mes projets <span aria-hidden="true">↗</span></a>
        </div>

        <nav class="personal-menu" aria-label="Découvrir mon portfolio">
          <div class="menu-topline">
            <span class="triangle-mark" aria-hidden="true"><i /><i /><i /></span>
            <span>Navigation</span>
          </div>
          <p class="menu-title" aria-hidden="true">Le menu.</p>
          <div class="menu-entries">
            <a v-for="item in menu" :key="item.href" :href="item.href" class="menu-entry">
              <span class="menu-index">{{ item.number }}</span>
              <span>{{ item.label }}</span>
              <span class="menu-arrow" aria-hidden="true">↗</span>
            </a>
          </div>
          <p class="menu-footnote">Houcine Drifi · Portfolio</p>
        </nav>
      </div>
      <div class="hero-bottom">
        <span>Développement web & applications</span>
        <a href="#a-propos">La suite juste en dessous <span aria-hidden="true">↓</span></a>
      </div>
    </section>

    <section id="a-propos" class="profile-section section-shell" tabindex="-1" aria-labelledby="profile-title">
      <div class="section-heading"><p class="eyebrow">01 / À propos</p></div>
      <div class="profile-layout">
        <div class="profile-title-block">
          <h2 id="profile-title">Un peu <br />de <span>moi.</span></h2>
          <a class="text-action profile-github" href="https://github.com/dhoucine62" target="_blank" rel="noopener noreferrer">
            Mon GitHub · dhoucine62 <span aria-hidden="true">↗</span>
          </a>
        </div>
        <div class="profile-copy">
          <p class="profile-intro">
            Ce qui me plaît dans le développement, c’est de comprendre comment
            une application fonctionne, puis d’essayer de la construire moi-même.
          </p>
          <p>
            Je suis étudiant en informatique. En formation, j’apprends notamment
            Java, Python, le développement web et les bases de données.
            À côté, j’essaie de mettre tout ça en pratique avec des projets personnels.
          </p>
        </div>
      </div>
    </section>

    <section id="competences" class="skills-section" tabindex="-1" aria-labelledby="skills-title">
      <div class="section-shell">
        <div class="section-heading"><p class="eyebrow">02 / Compétences</p></div>
        <div class="skills-heading">
          <h2 id="skills-title">Ce que <span>j’apprends.</span></h2>
          <p>Des langages vus en cours ou essayés dans mes projets.<br />Je continue à les pratiquer.</p>
        </div>
        <Competences />
        <p class="learning-line">En ce moment, j’expérimente aussi <strong>Vue</strong> et <strong>React</strong> pour les interfaces web.</p>
      </div>
    </section>

    <section id="projets" class="projects-section section-shell" tabindex="-1" aria-labelledby="projects-title">
      <div class="section-heading"><p class="eyebrow">03 / Projets</p></div>
      <div class="projects-heading">
        <h2 id="projects-title">Ce que <span>je fais.</span></h2>
        <p>Un mod Minecraft, un jeu de game jam et ce portfolio.</p>
      </div>
      <article class="project-card">
        <a class="project-visual project-screenshot" href="https://www.curseforge.com/minecraft/mc-mods/tdwcm" target="_blank" rel="noopener noreferrer" aria-label="Découvrir THE Doctor Who Client Mod sur CurseForge">
          <img src="/projects/tdwcm.png" alt="Deux TARDIS dans Minecraft, dont un ouvert sur son intérieur." width="1920" height="1017" loading="lazy" />
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
            <li>Minecraft</li><li>NeoForge</li><li>Modding</li>
          </ul>
          <a class="text-action" href="https://www.curseforge.com/minecraft/mc-mods/tdwcm" target="_blank" rel="noopener noreferrer">
            Voir sur CurseForge <span aria-hidden="true">↗</span>
          </a>
        </div>
      </article>
      <article class="project-card">
        <a class="project-visual project-screenshot" href="https://r0-m-1.itch.io/pyrotechclick" target="_blank" rel="noopener noreferrer" aria-label="Découvrir PyrotechClick sur itch.io">
          <img src="/projects/pyrotechclick.png" alt="Écran des commandes de PyrotechClick : déplacements, tirs et interactions à la souris." width="794" height="446" loading="lazy" />
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
            <li>Godot</li><li>2D</li><li>Game jam</li>
          </ul>
          <a class="text-action" href="https://r0-m-1.itch.io/pyrotechclick" target="_blank" rel="noopener noreferrer">
            Voir sur itch.io <span aria-hidden="true">↗</span>
          </a>
        </div>
      </article>
      <article class="project-card">
        <a class="project-visual" href="#accueil" aria-label="Revoir l’accueil de mon portfolio">
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
            <li>Vue 3</li><li>TypeScript</li><li>CSS</li>
          </ul>
          <a class="text-action" href="https://github.com/dhoucine62/portfolio" target="_blank" rel="noopener noreferrer">Voir le code sur GitHub <span aria-hidden="true">↗</span></a>
        </div>
      </article>
      <GithubStats />
    </section>
  </main>
</template>
