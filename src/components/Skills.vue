<template>
  <div id="competences" class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-base font-semibold text-blue-600 tracking-wide uppercase">Expertise & Outils</h2>
        <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
          Mes Compétences Techniques
        </p>
      </div>

      <div class="space-y-16">
        
        <div v-for="category in skillCategories" :key="category.name">
          
          <h3 class="text-xl font-bold text-gray-800 border-b-2 border-blue-200 pb-2 mb-8 inline-block">
            {{ category.name }}
          </h3>
          
          <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-6">
            
            <div v-for="skill in category.skills" :key="skill.name" class="bg-white p-6 rounded-xl shadow-sm border border-gray-100 text-center hover:shadow-md hover:border-blue-300 transition-all duration-300 group cursor-pointer">
              
              <div class="h-16 w-16 mx-auto bg-gray-50/50 rounded-lg flex items-center justify-center mb-4 group-hover:scale-110 group-hover:bg-blue-50 transition-all duration-300 p-2">
                <img :src="skill.svg" :alt="`Logo ${skill.name}`" class="w-full h-full object-contain drop-shadow-sm group-hover:drop-shadow-md transition-all" />
              </div>
              
              <h4 class="text-sm font-bold text-gray-900">{{ skill.name }}</h4>
              
            </div>

          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const skillCategories = ref([
  {
    name: 'Langages de programmation',
    skills: [
      { name: 'JavaScript', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg' },
      { name: 'Java', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg' },
      { name: 'Python', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg' }
    ]
  },
  {
    name: 'Développement Frontend',
    skills: [
      { name: 'Vue.js', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg' },
      { name: 'Next.js', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original.svg' },
      { name: 'HTML', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg' },
      { name: 'CSS', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg' }
    ]
  },
  {
    name: 'Développement Mobile',
    skills: [
      { name: 'Flutter', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/flutter/flutter-original.svg' }
    ]
  },
  {
    name: 'Bases de données',
    skills: [
      { name: 'SQL', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/azuresqldatabase/azuresqldatabase-original.svg' }
    ]
  },
  {
    name: 'IDE & Outils',
    skills: [
      { name: 'IntelliJ IDEA', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/intellij/intellij-original.svg' },
      { name: 'VS Code', svg: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vscode/vscode-original.svg' }
    ]
  }
]);
</script>