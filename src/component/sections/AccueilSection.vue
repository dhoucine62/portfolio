<script setup lang="ts">
const menu = [
  { label: 'À propos', href: '#a-propos', number: '01' },
  { label: 'Compétences', href: '#competences', number: '02' },
  { label: 'Projets', href: '#projets', number: '03' },
];
</script>

<template>
  <section
    id="accueil"
    class="hero section-shell"
    tabindex="-1"
    aria-labelledby="hero-title"
  >
    <div class="hero-layout">
      <div class="hero-copy">
        <h1 id="hero-title">
          HOUCINE<br /><span>DRIFI<span class="name-dot">.</span></span>
        </h1>
        <p class="hero-role">Étudiant en informatique</p>
        <p class="hero-description">
          J’apprends à développer des sites web et des applications.
          Ici, je partage ce que je fais et ce que j’apprends en chemin.
        </p>
        <a class="action action-red" href="#projets">
          Voir mes projets <span aria-hidden="true">↗</span>
        </a>
      </div>

      <nav class="personal-menu" aria-label="Découvrir mon portfolio">
        <div class="menu-topline">
          <span class="triangle-mark" aria-hidden="true">
            <i /><i /><i />
          </span>
          <span>Navigation</span>
        </div>
        <p class="menu-title" aria-hidden="true">Le menu.</p>
        <div class="menu-entries">
          <a
            v-for="item in menu"
            :key="item.href"
            :href="item.href"
            class="menu-entry"
          >
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
      <a href="#a-propos">
        La suite juste en dessous <span aria-hidden="true">↓</span>
      </a>
    </div>
  </section>
</template>
