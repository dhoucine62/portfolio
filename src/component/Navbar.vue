<script setup lang="ts">
const links = [
  { label: "Accueil", href: "#accueil" },
  { label: "À propos", href: "#a-propos" },
  { label: "Compétences", href: "#competences" },
  { label: "Projets", href: "#projets" },
];
</script>

<template>
  <header
    class="sticky top-0 z-10 border-b border-slate-200 bg-white/95 backdrop-blur"
  >
    <nav
      class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4"
      aria-label="Navigation principale"
    >
      <a href="#accueil" class="text-lg font-bold text-slate-900"
        >Houcine Drifi</a
      >

      <ul class="hidden items-center gap-8 md:flex">
        <li v-for="link in links" :key="link.href">
          <a
            :href="link.href"
            class="text-sm font-medium text-slate-600 transition hover:text-slate-900"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>
