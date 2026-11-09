<script setup lang="ts">
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="site-footer">
    <div class="section-shell footer-content">
      <div><p>Merci d’être passé.</p><span>© {{ currentYear }} Houcine Drifi — Tous droits réservés.</span></div>
      <a href="#accueil" class="back-top">Retour en haut <span aria-hidden="true">↑</span></a>
    </div>
  </footer>
</template>
