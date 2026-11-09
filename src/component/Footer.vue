<script setup lang="ts">
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="border-t border-slate-200 bg-slate-900 text-slate-300">
    <div
      class="mx-auto flex max-w-6xl flex-col items-center justify-between gap-2 px-6 py-6 text-sm sm:flex-row"
    >
      <p class="font-medium text-white">Houcine Drifi</p>
      <p>© {{ currentYear }} Houcine Drifi. Tous droits réservés.</p>
    </div>
  </footer>
</template>
