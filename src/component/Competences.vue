<script setup lang="ts">
const languages = [
  { label: "Java", icon: "Java" },
  { label: "JavaScript", icon: "JavaScript" },
  { label: "TypeScript", icon: "TypeScript" },
  { label: "Python", icon: "Python" },
  { label: "HTML/CSS", icon: "HTML" },
  { label: "SQL", icon: "SQL" },
  { label: "PHP", icon: "PHP" },
];
</script>

<template>
  <div>
    <h3 class="mt-5 text-2xl font-bold text-slate-900">
      Langages de programmation :
    </h3>
    <ul
      class="mx-auto flex max-w-6xl items-center justify-between gap-4 px-6 py-4"
    >
      <li
        v-for="language in languages"
        :key="language.label"
        class="rounded-xl border-2 border-indigo-500/60 bg-white/5 px-5 py-3 text-center shadow-md transition duration-300 hover:-translate-y-1 hover:border-indigo-400 hover:shadow-indigo-500/30"
      >
        <img
          :src="`/icon/${language.icon}.svg`"
          :alt="language.label"
          class="mx-auto block"
          height="64"
          width="64"
        />
        {{ language.label }}
      </li>
    </ul>
  </div>
</template>
