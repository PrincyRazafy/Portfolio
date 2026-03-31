<template>
  <section
    class="hero-section"
    id="accueil"
    ref="heroSection"
    :class="{ 'animate-in': isVisible }"
  >
    <div class="hero-background"></div>
    <div class="container hero-content">
      <div class="hero-text" :class="{ 'animate-in': isVisible }">
        <h1 class="display-4 fw-bold">
          Hi, I'm <span class="text-warning">Princy</span>
        </h1>
        <br />
        <p class="lead">
          Currently in my 3rd year at the National School of Informatics in
          Fianarantsoa, I specialize in software engineering and databases.
        </p>
        <p class="lead">
          Passionate about programming, game development and robotics.
        </p>
        <br />
        <div class="social-links">
          <a
            href="https://web.facebook.com/profile.php?id=61576537591892"
            class="social-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            <img src="@/assets/icons/facebook.png" alt="facebook" />
          </a>
          <a
            href="https://github.com/PrincyRazafy"
            class="social-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            <img src="@/assets/icons/github.png" alt="github" />
          </a>
          <a
            href="https://mail.google.com/mail/?view=cm&fs=1&to=princyyrazafindrainibe@gmail.com"
            class="social-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            <img src="@/assets/icons/gmail.png" alt="gmail" />
          </a>
          <a
            href="www.linkedin.com/in/princy-razafy-981b3a33a"
            class="social-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            <img src="@/assets/icons/linkedin.png" alt="linkedin" />
          </a>
        </div>
        <a
          href="@/assets/cv.pdf"
          class="download-cv"
          download
          target="_blank"
          rel="noopener noreferrer"
          @click="CV"
        >
          Download CV
        </a>
      </div>
      <div class="hero-image-container" :class="{ 'animate-in': isVisible }">
        <img :src="profileImage" alt="profile" class="profile-img" />
      </div>
    </div>
  </section>
</template>

<script setup>
import profileImage from "@/assets/profil.jpg";
import Swal from "sweetalert2";
import { onBeforeUnmount, onMounted, ref } from "vue";

const isVisible = ref(false);
const heroSection = ref(null);

let observer = null;

onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.intersectionRatio >= 0.45) {
        isVisible.value = true;
      } else {
        isVisible.value = false;
      }
    },
    {
      threshold: [0.45],
    },
  );

  if (heroSection.value) {
    observer.observe(heroSection.value);
  }
});

onBeforeUnmount(() => {
  if (observer) observer.disconnect();
});

function CV() {
  Swal.fire({
    title: "Patience !",
    text: "Le bouton n’est pas encore fonctionnel...",
    timer: 2000,
    timerProgressBar: true,
    didOpen: () => Swal.showLoading(),
  });
}
</script>

<style scoped>
.hero-section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  background-color: #121212;
  color: white;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(
    circle at 70% 40%,
    rgba(128, 0, 255, 0.3),
    transparent 50%
  );
  filter: blur(100px);
  z-index: 0;
}

.hero-content {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  text-align: center;
  padding-top: 5rem;
  padding-bottom: 5rem;
}

@media (min-width: 768px) {
  .hero-content {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }
}

.hero-text {
  max-width: 500px;
  opacity: 0;
  transform: translateX(-100px);
  transition: all 2.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.hero-text.animate-in {
  opacity: 1;
  transform: translateX(0);
}

.hero-image-container {
  margin-top: 3rem;
  text-align: center;
  opacity: 0;
  transform: translateX(100px);
  transition: all 2.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.hero-image-container.animate-in {
  opacity: 1;
  transform: translateX(0);
}

@media (min-width: 768px) {
  .hero-image-container {
    margin-top: 0;
  }
}

.hero-text.animate-in h1 {
  transition-delay: 0.4s;
}
.hero-text.animate-in p {
  transition-delay: 0.8s;
}
.hero-text.animate-in .social-links {
  transition-delay: 1.2s;
}

.social-links {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-top: 1.5rem;
}

@media (min-width: 768px) {
  .social-links {
    justify-content: flex-start;
  }
}

.social-link {
  width: 40px;
  height: 40px;
  background: transparent;
  border: 2px solid #00abf0;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  overflow: hidden;
  position: relative;
  transition: 0.5s;
}

.social-link::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 0;
  background: #00abf0;
  z-index: -1;
  transition: 0.5s;
}

.social-link:hover::before {
  width: 100%;
}

.social-link img {
  filter: brightness(0) invert(1);
  transition: 0.3s;
  width: 20px;
  height: 20px;
}

.social-link:hover img {
  filter: brightness(0);
}

.profile-img {
  width: 300px;
  height: 300px;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid #ffc107;
}

/*btn*/
.download-cv {
  display: inline-block;
  margin-top: 2rem;
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
  font-weight: 600;
  color: #121212;
  background-color: #ffc107;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease;
}

.download-cv:hover {
  background-color: #e6ac00;
  color: #fff;
  transform: translateY(-3px);
}
</style>
