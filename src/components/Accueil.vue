<template>
  <section
    class="accueil d-flex align-items-center justify-content-center animate-section"
    id="accueil"
  >
    <div class="text-center glass">
      <h1>RAZAFINDRAINIBE Ny Antsafitia Princy</h1>
    </div>
    <div class="bout">
      <a
        href="https://github.com/PrincyRazafy"
        target="_blank"
        rel="noopener noreferrer"
        class="btn btn-outline-light me-3"
      >
        GitHub
      </a>
      <button class="btn btn-outline-light me-3" @click="CV">
        Download CV
      </button>
    </div>
  </section>
</template>

<script setup>
import Swal from "sweetalert2";

function CV() {
  Swal.fire({
    title: "Patience !",
    text: "Le bouton n’est pas encore fonctionnel...",
    timer: 2000,
    timerProgressBar: true,
    didOpen: () => {
      Swal.showLoading();
    },
  });
}
</script>

<style scoped>
.accueil {
  min-height: 100vh;
  width: 100%;
  position: relative;
  margin: 0;
  font-family: "Segoe UI", sans-serif;
  background: linear-gradient(-45deg, #0f2027, #203a43, #2c5364, #0f2027);
  /* background: linear-gradient(-45deg, red, green, white, black); */
  /* background: linear-gradient(-45deg, #ff416c, #ff4b2b, #f9d423, #ff416c); */
  background-size: 400% 400%;
  animation: gradientMove 5s ease infinite;
  color: white;
  min-height: 100vh;
  overflow-x: hidden;
}

@keyframes gradientMove {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
.glass {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 2rem 3rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.bout {
  position: absolute;
  margin-top: 250px;
}
</style>
