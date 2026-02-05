<template>
  <section
    id="projet"
    class="py-8 sm:py-12 lg:py-16 min-h-screen flex flex-col items-center relative bg-[#121212] overflow-hidden"
  >
    <div class="projects-background"></div>

    <h1 class="mb-10 text-4xl title glow sm:text-5xl lg:text-6xl sm:mb-16">
      My Projects
    </h1>

    <div class="w-full swiper-container">
      <swiper
        :modules="modules"
        effect="coverflow"
        grab-cursor
        centered-slides
        :slides-per-view="'auto'"
        loop
        :autoplay="{
          delay: 3000,
          disableOnInteraction: false,
          pauseOnMouseEnter: true,
        }"
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        }"
        :coverflow-effect="{
          rotate: 0,
          stretch: 350,
          depth: 400,
          modifier: 2.8,
          slideShadows: true,
        }"
        class="my-swiper"
      >
        <!-- Projet 1 - Réel -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/LLRA.png"
                alt="EducTrack"
                class="object-cover w-full h-full"
              />
            </div>
            <div class="card-content">
              <h3>EducTrack</h3>
              <p>
                Application desktop dédiée à la gestion scolaire du Lycée
                Loterana Rakoto Andrianarijaona (LLRA).
              </p>
              <div class="tags">
                <span>#Java</span>
                <span>#Swing</span>
                <span>#MySQL</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>

        <!-- Projet 2 -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url(&quot;https://via.placeholder.com/800x600/1e293b/00f2ea?text=Portfolio+Site&quot;);
              "
            ></div>
            <div class="card-content">
              <h3>Portfolio Personnel</h3>
              <p>
                Site web moderne et animé présentant mes compétences et projets
                (ce site !).
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#Tailwind CSS</span>
                <span>#Swiper</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>

        <!-- Projet 3 -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url(&quot;https://via.placeholder.com/800x600/1e293b/00f2ea?text=E-commerce+App&quot;);
              "
            ></div>
            <div class="card-content">
              <h3>E-Shop Demo</h3>
              <p>
                Boutique en ligne avec panier, authentification et paiement
                simulé.
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#Pinia</span>
                <span>#Tailwind</span>
                <span>#Firebase</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>

        <!-- Projet 4 -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url(&quot;https://via.placeholder.com/800x600/1e293b/00f2ea?text=Task+Manager&quot;);
              "
            ></div>
            <div class="card-content">
              <h3>TaskFlow</h3>
              <p>
                Gestionnaire de tâches collaboratif avec drag & drop et
                notifications en temps réel.
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#VueUse</span>
                <span>#Supabase</span>
                <span>#Tailwind</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>

        <!-- Projet 5 -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url(&quot;https://via.placeholder.com/800x600/1e293b/00f2ea?text=Weather+App&quot;);
              "
            ></div>
            <div class="card-content">
              <h3>Meteo Madagascar</h3>
              <p>
                Application météo avec prévisions sur 7 jours, localisation et
                thèmes jour/nuit.
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#OpenWeather API</span>
                <span>#Tailwind</span>
                <span>#PWA</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>

      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </div>
  </section>
</template>

<script setup>
import { Autoplay, EffectCoverflow, Navigation } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
const modules = [Navigation, EffectCoverflow, Autoplay];
</script>

<style scoped>
/* ────────────────────────────────────────────── */
.min-h-screen {
  min-height: 100vh;
}
.projects-background {
  position: absolute;
  inset: 0;
  background: radial-gradient(
    circle at 70% 40%,
    rgba(128, 0, 255, 0.22),
    transparent 55%
  );
  filter: blur(100px);
  z-index: 0;
  pointer-events: none;
}

.title {
  font-weight: bold;
  text-align: center;
  position: relative;
  z-index: 1;
  color: #00f2ea;
  text-shadow:
    0 0 20px #00f2ea,
    0 0 40px #00f2ea,
    0 0 60px rgba(0, 242, 234, 0.5);
}

.swiper-container {
  position: relative;
  z-index: 1;
  padding: 0 1.5rem; /* mobile */
}

@media (min-width: 640px) {
  .swiper-container {
    padding: 0 4rem;
  }
}
@media (min-width: 1024px) {
  .swiper-container {
    padding: 0 8rem;
    max-width: 1700px;
    margin: 0 auto;
  }
}

.my-swiper {
  padding: 3rem 0;
}

/* Cartes responsive */
.project-slide {
  width: 280px !important;
  height: 420px;
  opacity: 0.45;
  transform: scale(0.82);
  transition: all 0.6s ease;
}

@media (min-width: 640px) {
  .project-slide {
    width: 340px !important;
    height: 480px;
  }
}

@media (min-width: 1024px) {
  .project-slide {
    width: 420px !important;
    height: 570px;
    opacity: 0.35;
    transform: scale(0.75);
  }
}

.project-slide.swiper-slide-active {
  opacity: 1 !important;
  transform: scale(1) !important;
}

.card {
  width: 100%;
  height: 100%;
  background: rgba(0, 242, 234, 0.05);
  border-radius: 24px;
  overflow: hidden;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(0, 242, 234, 0.25);
  display: flex;
  flex-direction: column;
}

@media (min-width: 1024px) {
  .card {
    border-radius: 32px;
    box-shadow: 0 25px 60px rgba(0, 0, 0, 0.9);
    backdrop-filter: blur(20px);
  }
}

.card-image {
  height: 60%;
  background-size: cover;
  background-position: center;
}
.card-content {
  padding: 1.5rem;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

@media (min-width: 1024px) {
  .card-content {
    padding: 2.2rem;
  }
}

.card-content h3 {
  font-size: 1.8rem;
  margin-bottom: 0.8rem;
  color: #00f2ea;
}

@media (min-width: 1024px) {
  .card-content h3 {
    font-size: 2.3rem;
  }
}

.card-content p {
  font-size: 1rem;
  opacity: 0.9;
  margin-bottom: 1rem;
  color: #e0e0e0;
}

@media (min-width: 1024px) {
  .card-content p {
    font-size: 1.15rem;
    margin-bottom: 1.5rem;
  }
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  margin-bottom: 1rem;
}

.tags span {
  background: rgba(0, 242, 234, 0.18);
  color: #00f2ea;
  padding: 0.4rem 1rem;
  border-radius: 9999px;
  font-size: 0.9rem;
  border: 1px solid rgba(0, 242, 234, 0.3);
}

@media (min-width: 1024px) {
  .tags {
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .tags span {
    padding: 0.6rem 1.4rem;
    font-size: 1rem;
  }
}

.links {
  display: flex;
  gap: 1.5rem;
}

.links a {
  color: #00f2ea;
  text-decoration: none;
  font-weight: bold;
  font-size: 1.05rem;
  position: relative;
  transition: all 0.3s ease;
}

.links a:hover {
  color: #ffffff;
  text-shadow: 0 0 10px #00f2ea;
}

.links a::after {
  content: "";
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -4px;
  left: 0;
  background-color: #00f2ea;
  transition: width 0.3s ease;
}

.links a:hover::after {
  width: 100%;
}

/* Flèches responsive */
.swiper-button-prev,
.swiper-button-next {
  width: 48px;
  height: 48px;
  background: #00f2ea;
  border-radius: 50%;
  top: 50%;
  transform: translateY(-50%);
  box-shadow: 0 0 25px rgba(0, 242, 234, 0.7);
  z-index: 10;
}

.swiper-button-prev:after,
.swiper-button-next:after {
  font-size: 20px !important;
  color: #000;
  font-weight: bold;
}

@media (min-width: 1024px) {
  .swiper-button-prev,
  .swiper-button-next {
    width: 70px;
    height: 70px;
    box-shadow: 0 0 40px rgba(0, 242, 234, 0.8);
  }
  .swiper-button-prev:after,
  .swiper-button-next:after {
    font-size: 32px !important;
  }
}

.swiper-button-prev {
  left: 8px;
}
.swiper-button-next {
  right: 8px;
}

@media (min-width: 640px) {
  .swiper-button-prev {
    left: 20px;
  }
  .swiper-button-next {
    right: 20px;
  }
}

@media (min-width: 1024px) {
  .swiper-button-prev {
    left: 50px;
  }
  .swiper-button-next {
    right: 50px;
  }
}
</style>
