<script setup lang="ts">
import { ref } from 'vue';

const filters = ['Tout', 'Web', 'Applications', 'Données'] as const;
type Filter = typeof filters[number];
const selectedFilter = ref<Filter>('Tout');
const languages = [
  { label: 'HTML / CSS', icon: 'HTML', category: 'Web', detail: 'Structure & interfaces' },
  { label: 'JavaScript', icon: 'JavaScript', category: 'Web', detail: 'Interactions web' },
  { label: 'TypeScript', icon: 'TypeScript', category: 'Web', detail: 'JavaScript typé' },
  { label: 'Java', icon: 'Java', category: 'Applications', detail: 'Programmation objet' },
  { label: 'Python', icon: 'Python', category: 'Applications', detail: 'Logique & scripts' },
  { label: 'SQL', icon: 'SQL', category: 'Données', detail: 'Bases de données' },
  { label: 'PHP', icon: 'PHP', category: 'Web', detail: 'Développement serveur' },
];
</script>

<template>
  <div class="skills-filter" role="group" aria-label="Filtrer les compétences">
    <button v-for="filter in filters" :key="filter" :class="{ selected: selectedFilter === filter }" :aria-pressed="selectedFilter === filter" @click="selectedFilter = filter">{{ filter }}</button>
  </div>
  <ul class="skills-grid" aria-live="polite" aria-label="Langages de programmation">
    <li v-for="language in languages" :key="language.label" class="skill-item"
      :class="{ 'is-filtered': selectedFilter !== 'Tout' && selectedFilter !== language.category }">
      <div class="skill-icon"><img :src="`/icon/${language.icon}.svg`" alt="" width="38" height="38" loading="lazy" /></div>
      <div><h3>{{ language.label }}</h3><p>{{ language.detail }}</p></div>
    </li>
  </ul>
</template>
