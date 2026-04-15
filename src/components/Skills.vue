<template>
  <section
    id="skills"
    ref="skillsSection"
    class="flex flex-col items-center justify-center w-full min-h-screen px-8 py-20 skills-section"
  >
    <div class="skills-background"></div>

    <h2
      class="mb-16 text-4xl font-bold tracking-tight text-white md:text-5xl lg:text-6xl"
      :class="{ 'animate-fade-in': isVisible }"
    >
      J'ai de l'expérience avec ces technologies :
    </h2>

    <div class="flex flex-wrap justify-center max-w-5xl gap-10 md:gap-12">
      <div
        v-for="(skill, index) in skills"
        :key="skill.name"
        class="relative mx-3 cursor-pointer group hidden-stagger"
        :class="{ 'animate-stagger': isVisible }"
        :style="{ animationDelay: `${index * 0.5}s` }"
        @mouseenter="showSwal(skill.name)"
        @mouseleave="hideSwal"
      >
        <img
          :src="skill.src"
          :alt="skill.name"
          class="w-24 h-24 mx-4 my-5 transition-all duration-300 opacity-70 group-hover:opacity-100 group-hover:scale-125"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import Swal from "sweetalert2";
import { onBeforeUnmount, onMounted, ref } from "vue";

const skills = [
  { name: "JavaScript", src: "/icons/javascript.svg" },
  { name: "React", src: "/icons/react.svg" },
  { name: "Vue.js", src: "/icons/vuejs.svg" },
  { name: "Figma", src: "/icons/figma.svg" },
  { name: "Laravel", src: "/icons/laravel.svg" },
  { name: "PHP", src: "/icons/php.svg" },
  { name: "Java", src: "/icons/java.svg" },
  { name: "C#", src: "/icons/csharp.svg" },
  { name: "Unity", src: "/icons/Unity.svg" },
  { name: "MySQL", src: "/icons/mysql.svg" },
  { name: "PostgreSQL", src: "/icons/postgresql.svg" },
  { name: "GitHub", src: "/icons/github.svg" },
  { name: "Git", src: "/icons/git.svg" },
  { name: "Python", src: "/icons/python.svg" },
];

const skillsSection = ref(null);
const isVisible = ref(false);

let observer = null;

const showSwal = (name) => {
  Swal.fire({
    title: name,
    position: "top",
    toast: true,
    showConfirmButton: false,
    timer: 999999,
    background: "#111827",
    color: "#fff",
  });
};

const hideSwal = () => {
  Swal.close();
};

onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true;
        observer.disconnect();
      }
    },
    { threshold: 0 },
  );

  if (skillsSection.value) observer.observe(skillsSection.value);
});

onBeforeUnmount(() => {
  if (observer) observer.disconnect();
  Swal.close();
});
</script>

<style scoped>
.skills-section {
  position: relative;
  overflow: hidden;
  background-color: rgb(78, 72, 72);
}

.skills-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background:
    radial-gradient(
      circle at 30% 60%,
      rgba(3, 146, 202, 0.25),
      transparent 50%
    ),
    radial-gradient(circle at 70% 30%, rgba(238, 182, 14, 0.2), transparent 50%);
  filter: blur(100px);
  z-index: 0;
}

.skills-section > *:not(.skills-background) {
  position: relative;
  z-index: 1;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px) scale(0.8);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.animate-fade-in {
  opacity: 0;
  animation: fadeIn 1s ease-out forwards;
}

.hidden-stagger {
  opacity: 0;
}

.animate-stagger {
  animation: fadeInUp 0.8s ease-out forwards;
}
</style>
