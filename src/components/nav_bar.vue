<template>
  <nav
    class="navbar navbar-expand-lg navbar-dark bg-dark px-4 fixed-bottom fixed-lg-top"
  >
    <div class="container-fluid d-flex justify-content-between">
      <button class="btn btn-outline-light me-3" @click="CV">
        Download CV
      </button>

      <ul class="navbar-nav ms-auto gap-3 d-flex flex-row flex-lg-row">
        <li v-for="(item, index) in items" :key="index" class="nav-item">
          <a class="nav-link" :href="lien[index]">{{ item }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import Swal from "sweetalert2";
import { ref } from "vue";

const items = ref(["Accueil", "About", "Skills", "Projet", "Contact"]);

const lien = ref(["#accueil", "#about", "#skills", "#projet", "#contact"]);

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
@media (max-width: 991.98px) {
  .navbar {
    top: auto !important;
    bottom: 0 !important;
  }
}

@media (min-width: 992px) {
  .navbar {
    top: 0 !important;
    bottom: auto !important;
  }
}

/* color: #ffe082 !important; */
/* color: #ffd700 !important; */
</style>
