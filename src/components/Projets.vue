

<template>
  <div id="projets" class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-base font-semibold text-blue-600 tracking-wide uppercase">Portfolio</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
          Mes Réalisations
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="project in projects" :key="project.title" class="bg-white rounded-xl shadow-sm border border-gray-100 overflow-hidden hover:shadow-lg transition-shadow duration-300 flex flex-col">
          
          <div class="h-48 bg-gray-200 flex items-center justify-center text-gray-500 relative overflow-hidden">
            <img v-if="project.img" :src="project.img" :alt="`Aperçu de ${project.title}`" class="w-full h-full object-cover">
            <span v-else class="text-sm font-medium">[Image: {{ project.title }}]</span>
          </div>

          <div class="p-6 flex flex-col flex-1">
            <h3 class="text-xl font-bold text-gray-900 mb-2">{{ project.title }}</h3>
            <p class="text-gray-600 mb-4 flex-1">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 mb-4">
              <span v-for="tech in project.techs" :key="tech" class="px-3 py-1 bg-blue-50 text-blue-600 text-xs font-semibold rounded-full">
                {{ tech }}
              </span>
            </div>
            
            <a :href="project.link" target="_blank" class="text-blue-600 hover:text-blue-800 font-medium text-sm flex items-center mt-auto">
              Voir le projet &rarr;
            </a>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import tdwcm from "@/assets/tdwcm.png"
import { ref } from 'vue';

const projects = ref([
  {
    title: 'THE Doctor Who Client Mod',
    description: 'Un mod pour Minecraft plongeant les joueurs dans l\'univers de Doctor Who, enrichissant l\'expérience de jeu avec de nouveaux éléments visuels et mécaniques.',
    techs: ['Java', 'NeoForge', 'Minecraft API'],
    link: 'https://www.curseforge.com/minecraft/mc-mods/tdwcm',
    img: tdwcm
  },
  {
    title: 'placeholder',
    description: 'placeholder',
    techs: ['placeholder'],
    link: 'https://github.com/dhoucine62/placeholder',
    img: ''
  },
  {
    title: 'placeholder',
    description: 'placeholder',
    techs: ['placeholder'],
    link: 'https://github.com/dhoucine62/placeholder',
    img: ''
  }
]);
</script>