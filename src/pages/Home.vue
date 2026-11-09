<script setup lang="ts">
import Competences from "@/component/Competences.vue";

const birthDate = new Date(2007, 1, 27);

function age() {
  const today = new Date();
  let calculatedAge = today.getFullYear() - birthDate.getFullYear();
  return calculatedAge;
}
</script>

<template>
  <main>
    <section id="accueil" class="mx-auto max-w-6xl px-6 py-24 text-center">
      <p class="mb-3 font-medium text-sky-600">Développeur web</p>
      <h1 class="text-5xl font-bold tracking-tight text-slate-900 md:text-6xl">
        Houcine Drifi
      </h1>
      <p class="mt-6 max-w-xl text-lg text-slate-600"></p>
    </section>

    <section id="a-propos" class="bg-slate-100 space-y-4">
      <div class="mx-auto max-w-6xl px-6 py-24f">
        <h2 class="text-3xl font-bold text-slate-900">À propos de moi</h2>

        <div class="mt-6 space-y-4 text-lg leading-8 text-slate-700">
          <p>
            Bonjour, je m'appelle Houcine Drifi, j'ai
            <strong>{{ age() }} ans</strong> et je suis étudiant en
            informatique.
          </p>

          <p>
            Je suis passionné par le développement d'application et par la
            création de sites modernes, accessibles et agréables à utiliser.
            J'aime comprendre comment les applications fonctionnent et trouver
            des solutions aux problèmes techniques.
          </p>

          <p>
            Au cours de ma formation, j'apprends plusieurs technologies comme le
            Java, le HTML, le CSS, le JavaScript ainsi que le python et le SQL.
            Je suis en train d'expérimenter les frameworks comme le Vue et le
            React pour la conception de site internet.
          </p>

          <p>
            Je cherche constamment à améliorer mes compétences en réalisant des
            projets personnels. Chaque projet me permet de progresser,
            d'expérimenter de nouvelles idées et de mieux comprendre le monde du
            développement.
          </p>

          <p>
            Mon objectif est de continuer à apprendre et de devenir un
            développeur capable de créer des expériences web utiles,
            performantes et accessibles à tous.
          </p>
        </div>
      </div>
    </section>

    <section id="competences" class="mx-auto max-w-6xl px-6 py-24">
      <h2 class="text-3xl font-bold text-slate-900">Compétences</h2>

      <Competences />
    </section>

    <section id="projets" class="mx-auto max-w-6xl px-6 py-24">
      <h2 class="text-3xl font-bold text-slate-900">Projets</h2>
    </section>
  </main>
</template>
