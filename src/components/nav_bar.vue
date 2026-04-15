<template>
  <nav
    class="navbar navbar-expand-lg fixed-top"
    :class="{ 'navbar-scrolled': isScrolled }"
  >
    <div
      class="px-3 container-fluid d-flex justify-content-between flex-nowrap align-items-center px-lg-5"
    >
      <button class="flex-shrink-0 btn btn-outline-light me-3" @click="CV">
        <span class="d-none d-lg-inline">Download CV</span>
        <span class="d-inline d-lg-none">CV</span>
      </button>

      <ul
        class="flex-row gap-2 overflow-x-auto navbar-nav ms-auto gap-lg-4 hide-scrollbar"
      >
        <li
          v-for="item in navItems"
          :key="item.href"
          class="nav-item text-nowrap"
        >
          <a
            class="nav-link"
            :href="item.href"
            :class="{ active: activeSection === item.href }"
          >
            {{ item.label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import Swal from "sweetalert2";
import { onMounted, onUnmounted, ref } from "vue";

const navItems = [
  { label: "Home", href: "#accueil" },
  { label: "About", href: "#about" },
  { label: "Skills", href: "#skills" },
  { label: "Projects", href: "#projet" },
  { label: "Contact", href: "#contact" },
];

const activeSection = ref("#accueil");
const isScrolled = ref(false);

let ticking = false;

// detection de la section active et changement de style de la navbar au scroll
const updateActiveSection = () => {
  const sections = navItems.map((item) => item.href.replace("#", ""));
  let current = "#accueil";

  for (const sectionId of sections) {
    const element = document.getElementById(sectionId);
    if (element) {
      const rect = element.getBoundingClientRect();

      if (rect.top <= 150 && rect.bottom >= 100) {
        current = "#" + sectionId;
        break;
      }
    }
  }

  activeSection.value = current;
};

const handleScroll = () => {
  if (!ticking) {
    window.requestAnimationFrame(() => {
      updateActiveSection();
      isScrolled.value = window.scrollY > 50;
      ticking = false;
    });
    ticking = true;
  }
};

const handleHashChange = () => {
  activeSection.value = window.location.hash || "#accueil";
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll, { passive: true });
  window.addEventListener("hashchange", handleHashChange);

  // Vérification initiale
  setTimeout(() => {
    updateActiveSection();
    isScrolled.value = window.scrollY > 50;
  }, 300);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
  window.removeEventListener("hashchange", handleHashChange);
});

function CV() {
  Swal.fire({
    title: "Patience !",
    text: "Le CV sera bientôt disponible",
    timer: 2000,
    timerProgressBar: true,
    didOpen: () => Swal.showLoading(),
  });
}
</script>

<style scoped>
.navbar {
  background: rgba(18, 18, 18, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  transition: all 0.4s ease;
  z-index: 1030;
  padding: 0.8rem 0;
}

.navbar-scrolled {
  background: rgba(15, 23, 42, 0.95);
  backdrop-filter: blur(16px);
}

.nav-link {
  color: #e0e0e0 !important;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover,
.nav-link.active {
  color: #ffc107 !important;
}

.nav-link.active::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background: #ffc107;
}

@media (max-width: 991.98px) {
  .navbar {
    position: fixed !important;
    top: auto !important;
    bottom: 0 !important;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    border-bottom: none;
  }
}

.hide-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
</style>
