<script setup lang="ts">
import Competences from '@/component/Competences.vue';
</script>

<template>
  <section
    id="competences"
    class="skills-section"
    tabindex="-1"
    aria-labelledby="skills-title"
  >
    <div class="section-shell">
      <div class="section-heading">
        <p class="eyebrow">02 / Compétences</p>
      </div>
      <div class="skills-heading">
        <h2 id="skills-title">Ce que <span>j’apprends.</span></h2>
        <p>
          Des langages vus en cours ou essayés dans mes projets.<br />Je continue à les pratiquer.
        </p>
      </div>
      <Competences />
      <p class="learning-line">
        En ce moment, j’expérimente aussi <strong>Vue</strong> et <strong>React</strong> pour les interfaces web.
      </p>
    </div>
  </section>
</template>
