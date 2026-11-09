<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';

const links = [
  { label: 'Accueil', href: '#accueil', number: '01' },
  { label: 'À propos', href: '#a-propos', number: '02' },
  { label: 'Compétences', href: '#competences', number: '03' },
  { label: 'Projets', href: '#projets', number: '04' },
];
const activeSection = ref('#accueil');
let observer: IntersectionObserver | undefined;

function printCV() { window.print(); }
function handleShortcut(event: KeyboardEvent) {
  const target = event.target;
  if (event.altKey || event.ctrlKey || event.metaKey || event.shiftKey ||
    (target instanceof HTMLElement && (target.isContentEditable || /^(INPUT|TEXTAREA|SELECT)$/.test(target.tagName)))) return;
  const link = links[Number(event.key) - 1];
  if (link && /^[1-4]$/.test(event.key)) {
    event.preventDefault();
    document.querySelector<HTMLElement>(link.href)?.focus({ preventScroll: true });
    window.location.hash = link.href;
  }
}
onMounted(() => {
  observer = new IntersectionObserver((entries) => {
    for (const entry of entries) {
      if (entry.isIntersecting) activeSection.value = `#${entry.target.id}`;
    }
  }, { rootMargin: '-15% 0px -55% 0px', threshold: 0 });
  for (const link of links) {
    const section = document.querySelector(link.href);
    if (section) observer.observe(section);
  }
  window.addEventListener('keydown', handleShortcut);
});
onUnmounted(() => {
  observer?.disconnect();
  window.removeEventListener('keydown', handleShortcut);
});
</script>

<template>
  <a class="skip-link" href="#accueil">Aller au contenu</a>
  <header class="site-header">
    <a class="brand" href="#accueil" aria-label="Houcine Drifi — accueil">
      <span class="brand-mark">h<span>d</span>.</span>
      <span class="brand-caption">Houcine Drifi<span>Portfolio</span></span>
    </a>
    <nav class="main-nav" aria-label="Navigation principale">
      <a v-for="link in links" :key="link.href" :href="link.href"
        :class="['nav-link', { 'is-active': activeSection === link.href }]"
        :aria-current="activeSection === link.href ? 'location' : undefined">
        <span class="nav-number">{{ link.number }}</span><span>{{ link.label }}</span>
      </a>
    </nav>
    <button class="print-button" @click="printCV" aria-label="Imprimer ou enregistrer le CV en PDF">
      Mon CV <span aria-hidden="true">↗</span>
    </button>
  </header>
</template>
