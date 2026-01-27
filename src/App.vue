<template>
  <div class="overflow-hidden bg-dark text-light min-vh-100 position-relative">
    <Navbar />
    <Accueil />
    <HeroSection />
    <Skills />
    <Projet />
    <Contact />
  </div>
</template>

<script setup>
import Accueil from "./components/Accueil.vue";
import Contact from "./components/Contact.vue";
import HeroSection from "./components/HeroSection.vue";
import Navbar from "./components/nav_bar.vue";
import Projet from "./components/Projet.vue";
import Skills from "./components/Skills.vue";
</script>
