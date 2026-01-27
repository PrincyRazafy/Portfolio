<template>
  <section
    id="projet"
    class="section-full-height d-flex flex-column align-items-center py-5"
    style="position: relative; background-color: #121212"
  >
    <!-- Fond radial violet flou conservé mais légèrement adouci -->
    <div class="projects-background"></div>

    <h1 class="title glow">My Projects</h1>

    <div class="swiper-container">
      <swiper
        :modules="modules"
        :effect="'coverflow'"
        :grab-cursor="true"
        :centered-slides="true"
        :slides-per-view="'auto'"
        :loop="true"
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
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/LLRA.png"
                alt="Projet 1"
                class="w-full h-full object-cover"
              />
            </div>
            <div class="card-content">
              <h3>EducTrack</h3>
              <p>
                Application desktop dédiée à la gestion scolaire du le Lycée
                Loterana Rakoto Andrianarijaona (LLRA).
              </p>
              <div class="tags">
                <span>#Java</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url('https://via.placeholder.com/800x600?text=Projet+1');
              "
            ></div>
            <div class="card-content">
              <h3>Projet 2</h3>
              <p>Description du projet...</p>
              <div class="tags">
                <span>#Vue.js</span><span>#Tailwind</span><span>#Firebase</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url('https://via.placeholder.com/800x600?text=Projet+1');
              "
            ></div>
            <div class="card-content">
              <h3>Projet 3</h3>
              <p>Description du projet...</p>
              <div class="tags">
                <span>#Vue.js</span><span>#Tailwind</span><span>#Firebase</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url('https://via.placeholder.com/800x600?text=Projet+1');
              "
            ></div>
            <div class="card-content">
              <h3>Projet 4</h3>
              <p>Description du projet...</p>
              <div class="tags">
                <span>#Vue.js</span><span>#Tailwind</span><span>#Firebase</span>
              </div>
              <div class="links">
                <a href="#" target="_blank">Live Demo</a>
                <a href="#" target="_blank">View Code</a>
              </div>
            </div>
          </div>
        </swiper-slide>
        <swiper-slide class="project-slide">
          <div class="card">
            <div
              class="card-image"
              style="
                background-image: url('https://via.placeholder.com/800x600?text=Projet+1');
              "
            ></div>
            <div class="card-content">
              <h3>Projet 5</h3>
              <p>Description du projet...</p>
              <div class="tags">
                <span>#Vue.js</span><span>#Tailwind</span><span>#Firebase</span>
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
.section-full-height {
  min-height: 100vh;
  width: 100%;
  color: white;
  overflow: hidden;
}

/* Fond violet flou légèrement réduit en intensité pour ne pas écraser les nouveaux tons cyan */
.projects-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(
    circle at 70% 40%,
    rgba(128, 0, 255, 0.25),
    transparent 50%
  );
  filter: blur(120px);
  z-index: 0;
}

.title {
  font-size: 4rem;
  font-weight: bold;
  margin: 2rem 0 4rem;
  text-align: center;
  position: relative;
  z-index: 1;
  color: #00f2ea; /* Cyan néon principal */
}

.glow {
  text-shadow: 0 0 20px #00f2ea, 0 0 40px #00f2ea,
    0 0 60px rgba(0, 242, 234, 0.6);
}

.swiper-container {
  width: 100%;
  max-width: 1700px;
  padding: 0 150px;
  position: relative;
  z-index: 1;
}

.my-swiper {
  padding: 60px 0;
}

.project-slide {
  width: 420px !important;
  height: 570px;
  opacity: 0.35;
  transform: scale(0.75);
  transition: all 0.7s ease;
}

.project-slide.swiper-slide-active {
  opacity: 1;
  transform: scale(1);
}

.card {
  width: 100%;
  height: 100%;
  background: rgba(
    0,
    242,
    234,
    0.05
  ); /* Légère teinte cyan dans le fond verre */
  border-radius: 32px;
  overflow: hidden;
  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.9);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(0, 242, 234, 0.3); /* Bordure cyan */
  display: flex;
  flex-direction: column;
}

.card-image {
  height: 62%;
  background-size: cover;
  background-position: center;
}

.card-content {
  padding: 2.2rem;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: white;
}

.card-content h3 {
  font-size: 2.3rem;
  margin-bottom: 1rem;
  color: #00f2ea;
}

.card-content p {
  opacity: 0.9;
  margin-bottom: 1.5rem;
  font-size: 1.15rem;
  color: #e0e0e0;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.tags span {
  background: rgba(0, 242, 234, 0.2);
  color: #00f2ea;
  padding: 0.6rem 1.4rem;
  border-radius: 30px;
  font-size: 1rem;
  border: 1px solid rgba(0, 242, 234, 0.4);
}

.links {
  display: flex;
  gap: 2rem;
}

.links a {
  color: #00f2ea;
  text-decoration: none;
  font-weight: bold;
  font-size: 1.2rem;
  position: relative;
  transition: all 0.3s ease;
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

.links a:hover {
  color: #ffffff;
  text-shadow: 0 0 10px #00f2ea;
}

.links a:hover::after {
  width: 100%;
}

/* Flèches de navigation en cyan */
.swiper-button-prev,
.swiper-button-next {
  width: 70px;
  height: 70px;
  background: #00f2ea;
  border-radius: 50%;
  top: 50%;
  transform: translateY(-50%);
  box-shadow: 0 0 40px rgba(0, 242, 234, 0.8);
  z-index: 2;
}

.swiper-button-prev:after,
.swiper-button-next:after {
  font-size: 32px;
  color: #000;
  font-weight: bold;
}

.swiper-button-prev {
  left: 50px;
}

.swiper-button-next {
  right: 50px;
}
</style>
