<script setup lang="ts">
import HeroSection from './components/HeroSection.vue';
import Navbar from './components/Navbar.vue';
import Projets from './components/Projets.vue';
import Footer from './components/Footer.vue';
import Skills from './components/Skills.vue';

</script>

<template>
  <Navbar />
  <HeroSection />
  <Projets />
  <Skills />
  <Footer></Footer>
  
</template>

<style>
html {
  scroll-behavior: smooth;
  background-color: #0f172a;
}
</style>