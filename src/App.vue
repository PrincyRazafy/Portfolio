<template>
  <div class="overflow-hidden bg-dark text-light min-vh-100 position-relative">
    <Navbar />
    <HeroSection />
    <About />
    <Skills />
    <Projet />
    <Contact />
  </div>
</template>

<script setup>
import { onMounted, onUnmounted } from "vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";
import HeroSection from "./components/HeroSection.vue";
import Navbar from "./components/nav_bar.vue";
import Projet from "./components/Projet.vue";
import Skills from "./components/Skills.vue";

let observer = null;

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("section-visible");
        } else {
          entry.target.classList.remove("section-visible");
        }
      });
    },
    {
      threshold: 0.12,
      rootMargin: "0px 0px -80px 0px",
    },
  );

  document.querySelectorAll(".animate-section").forEach((el) => {
    observer.observe(el);
  });
});

onUnmounted(() => {
  if (observer) observer.disconnect();
});
</script>

<style scoped>
.animate-section {
  opacity: 0;
  transform: translateY(60px);
  transition:
    opacity 0.9s cubic-bezier(0.16, 1, 0.3, 1),
    transform 0.9s cubic-bezier(0.16, 1, 0.3, 1);
  will-change: opacity, transform; /* améliore la fluidité */
}

.section-visible {
  opacity: 1;
  transform: translateY(0);
}

#accueil.animate-section {
  transform: translateY(70px) scale(0.96);
  transition-duration: 1.1s;
  transition-delay: 0.3s;
}

#accueil.section-visible {
  transform: translateY(0) scale(1);
}

#projet.animate-section {
  transform: translateY(90px) scale(0.94);
  transition-duration: 1.05s;
  transition-delay: 0.22s;
}

#projet.section-visible {
  transform: translateY(0) scale(1);
}

#projet.section-visible .my-swiper {
  opacity: 0;
  transform: scale(0.92);
  transition:
    opacity 1.3s ease-out 0.45s,
    transform 1.3s cubic-bezier(0.34, 1.56, 0.64, 1) 0.45s;
}

#projet:not(.section-visible) .my-swiper {
  opacity: 0;
  transform: scale(0.92);
}

#contact.animate-section {
  transform: translateY(120px);
  transition-duration: 1.2s;
  transition-delay: 0.32s;
}

#contact.section-visible {
  transform: translateY(0);
}
</style>
