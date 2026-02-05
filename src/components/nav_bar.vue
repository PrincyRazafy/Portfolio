<template>
  <nav
    class="px-4 navbar navbar-expand-lg navbar-dark bg-dark fixed-bottom fixed-lg-top"
  >
    <div class="container-fluid d-flex justify-content-between">
      <button class="btn btn-outline-light me-3" @click="CV">
        <span class="d-none d-lg-inline">Download CV</span>
        <span class="d-inline d-lg-none">CV</span>
      </button>

      <ul class="flex-row gap-3 navbar-nav ms-auto d-flex">
        <li v-for="item in filteredItems" :key="item.href" class="nav-item">
          <a class="nav-link" :href="item.href">
            {{ item.label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import Swal from "sweetalert2";
import { computed, onMounted, onUnmounted, ref } from "vue";

const navItems = [
  { label: "Accueil", href: "#accueil" },
  { label: "About", href: "#about" },
  { label: "Skills", href: "#skills" },
  { label: "Projet", href: "#projet" },
  { label: "Contact", href: "#contact" },
];

const activeHash = ref(window.location.hash || "#accueil");
const isMobile = ref(window.innerWidth < 992);

const handleResize = () => {
  isMobile.value = window.innerWidth < 992;
};

const handleHashChange = () => {
  activeHash.value = window.location.hash;
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
  window.addEventListener("hashchange", handleHashChange);
});

onUnmounted(() => {
  window.removeEventListener("resize", handleResize);
  window.removeEventListener("hashchange", handleHashChange);
});

/* ✅ Index SAFE */
const filteredItems = computed(() => {
  if (!isMobile.value) return navItems;

  return navItems.filter((item) => item.href !== activeHash.value);
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
