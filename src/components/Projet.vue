<template>
  <section
    id="projet"
    class="py-8 sm:py-12 lg:py-16 min-h-screen flex flex-col items-center relative bg-[#121212] overflow-hidden"
  >
    <div class="projects-background"></div>
    <br />
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
        <!-- eductrack -->
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
                <span>#PostgreSql</span>
              </div>
            </div>
          </div>
        </swiper-slide>
        <!-- Portfolio -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/portfolio.png"
                alt="Portfolio"
                class="object-cover w-full h-full"
              />
            </div>
            <div class="card-content">
              <h3>Portfolio Personnel</h3>
              <p>
                Portfolio personnel moderne et animé présentant mes compétences
                et projets.
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#Tailwind CSS</span>
              </div>
              <div class="links">
                <a
                  href="https://portfolio-princy-razafindrainibe.vercel.app/"
                  target="_blank"
                  translate="no"
                  >Live Demo</a
                >
                <a
                  href="https://github.com/PrincyRazafy/Portfolio.git"
                  target="_blank"
                  translate="no"
                  >View Code</a
                >
              </div>
            </div>
          </div>
        </swiper-slide>
        <!-- phone -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/csharp.jpg"
                alt="mobilix"
                class="object-cover w-full h-full"
              />
            </div>
            <div class="card-content">
              <h3>Mobilix</h3>
              <p>Application desktop de commande et livraison de téléphones.</p>
              <div class="tags">
                <span>#Csharp</span>
                <span>#MySql</span>
              </div>
              <div class="links">
                <a
                  href="https://github.com/PrincyRazafy/Commande_Livraison_telephone.git"
                  target="_blank"
                  translate="no"
                  >View Code</a
                >
              </div>
            </div>
          </div>
        </swiper-slide>
        <!-- SIGAC -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/SIGAC.png"
                alt="SIGAC"
                class="object-contain w-full h-full"
              />
            </div>
            <div class="card-content">
              <h3>SIGAC</h3>
              <p>
                Application web dédiée à la gestion des absences et congés du
                SRB-HM.
              </p>
              <div class="tags">
                <span>#React</span>
                <span>#Laravel</span>
              </div>
            </div>
          </div>
        </swiper-slide>
        <!-- Portfolio -->
        <swiper-slide class="project-slide">
          <div class="card">
            <div class="card-image">
              <img
                src="@/assets/portfolio.png"
                alt="Portfolio"
                class="object-cover w-full h-full"
              />
            </div>
            <div class="card-content">
              <h3>Portfolio Personnel</h3>
              <p>
                Portfolio personnel moderne et animé présentant mes compétences
                et projets.
              </p>
              <div class="tags">
                <span>#Vue.js</span>
                <span>#Tailwind CSS</span>
              </div>
              <div class="links">
                <a
                  href="https://portfolio-princy-razafindrainibe.vercel.app/"
                  target="_blank"
                  translate="no"
                  >Live Demo</a
                >
                <a
                  href="https://github.com/PrincyRazafy/Portfolio.git"
                  target="_blank"
                  translate="no"
                  >View Code</a
                >
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
  padding: 0 1.5rem;
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

/* resp */
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
