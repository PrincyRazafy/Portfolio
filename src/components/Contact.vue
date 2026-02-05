<template>
  <section
    class="contact-section min-vh-100 d-flex align-items-center animate-section"
    id="contact"
  >
    <div class="container">
      <div class="mb-5 text-center">
        <h2 class="mb-3 text-white display-4 fw-bold">Contact</h2>
        <p class="max-w-2xl mx-auto lead text-white-70">
          N’hésitez pas à me contacter pour discuter de vos projets
        </p>
      </div>

      <div class="row g-5 align-items-start">
        <!-- Colonne des infos contact -->
        <div class="col-lg-5">
          <div class="gap-5 d-flex flex-column">
            <div class="info-item d-flex align-items-center">
              <div class="icon-wrapper me-4">
                <i class="bi bi-envelope-fill"></i>
              </div>
              <div>
                <h5 class="mb-1 text-white fw-semibold">Email</h5>
                <p class="mb-0 text-white-60">
                  princyyrazafindrainibe@gmail.com
                </p>
              </div>
            </div>

            <div class="info-item d-flex align-items-center">
              <div class="icon-wrapper me-4">
                <i class="bi bi-telephone-fill"></i>
              </div>
              <div>
                <h5 class="mb-1 text-white fw-semibold">Téléphone</h5>
                <p class="mb-0 text-white-60">+261 34 27 014 34</p>
              </div>
            </div>

            <div class="info-item d-flex align-items-center">
              <div class="icon-wrapper me-4">
                <i class="bi bi-geo-alt-fill"></i>
              </div>
              <div>
                <h5 class="mb-1 text-white fw-semibold">Localisation</h5>
                <p class="mb-0 text-white-60">Madagascar</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Formulaire -->
        <div class="pb-5 col-lg-7">
          <div class="p-5 shadow-2xl glass-card p-xl-6">
            <form
              @submit.prevent="submitForm"
              class="needs-validation"
              novalidate
            >
              <div class="mb-4">
                <label for="fullName" class="text-white form-label fw-medium"
                  >Nom complet</label
                >
                <input
                  type="text"
                  class="form-control form-control-lg modern-input"
                  id="fullName"
                  v-model="form.fullName"
                  placeholder="Votre nom complet"
                  required
                />
              </div>

              <div class="mb-4">
                <label for="email" class="text-white form-label fw-medium"
                  >Email</label
                >
                <input
                  type="email"
                  class="form-control form-control-lg modern-input"
                  id="email"
                  v-model="form.email"
                  placeholder="votre@email.com"
                  required
                />
              </div>

              <div class="mb-5">
                <label for="message" class="text-white form-label fw-medium"
                  >Message</label
                >
                <textarea
                  class="form-control form-control-lg modern-input"
                  id="message"
                  rows="6"
                  v-model="form.message"
                  placeholder="Décrivez votre projet ou posez-moi votre question..."
                  required
                ></textarea>
              </div>

              <button
                type="submit"
                class="btn btn-primary btn-lg w-100 modern-btn"
                :disabled="isLoading"
              >
                <span v-if="!isLoading">
                  <i class="bi bi-send-fill me-2"></i>
                  Envoyer le message
                </span>
                <span v-else>
                  <span class="spinner"></span>
                  Envoi en cours...
                </span>
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import emailjs from "@emailjs/browser"; // Changement uniquement ici
import Swal from "sweetalert2";
import { ref } from "vue";

const form = ref({ fullName: "", email: "", message: "" });
const isLoading = ref(false);

const submitForm = async () => {
  isLoading.value = true;

  try {
    await emailjs.send(
      "service_78u372d",
      "template_13uxmgr",
      {
        fullName: form.value.fullName,
        email: form.value.email,
        message: form.value.message,
      },
      "GDSgQSggUY5Cmgu63", // Public key
    );

    Swal.fire({
      icon: "success",
      title: "Message envoyé !",
      text: "Merci pour votre message, je vous répondrai très vite !",
      toast: true,
      position: "top-end",
      timer: 3000,
      timerProgressBar: true,
      showConfirmButton: false,
      background: "#1aae8d",
      color: "#fff",
      iconColor: "#fff",
    });

    form.value = { fullName: "", email: "", message: "" };
  } catch (error) {
    console.error(error);
    Swal.fire({
      icon: "error",
      title: "Oups...",
      text: "Une erreur est survenue. Réessayez ou contactez-moi directement par email.",
      confirmButtonColor: "#1aae8d",
    });
  } finally {
    isLoading.value = false;
  }
};
</script>

<style scoped>
.contact-section {
  min-height: 100vh;
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
  position: relative;
  overflow: hidden;
}

.contact-section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background:
    radial-gradient(
      circle at 20% 80%,
      rgba(26, 174, 141, 0.15) 0%,
      transparent 50%
    ),
    radial-gradient(
      circle at 80% 20%,
      rgba(59, 130, 246, 0.1) 0%,
      transparent 50%
    );
  pointer-events: none;
}

.glass-card {
  background: rgba(30, 41, 59, 0.65);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1.5rem;
}

.icon-wrapper {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #1aae8d, #16a085);
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  font-size: 1.4rem;
  color: #fff;
  flex-shrink: 0;
  box-shadow: 0 8px 25px rgba(26, 174, 141, 0.3);
}

.modern-input {
  background: rgba(15, 23, 42, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.15);
  color: #fff;
  border-radius: 1rem;
  transition: all 0.3s ease;
}

.modern-input::placeholder {
  color: #94a3b8;
}

.modern-input:focus {
  background: rgba(15, 23, 42, 0.8);
  border-color: #1aae8d;
  box-shadow: 0 0 0 4px rgba(26, 174, 141, 0.25);
  color: #fff;
}

.modern-btn {
  background: linear-gradient(135deg, #1aae8d, #16a085);
  border: none;
  border-radius: 1rem;
  font-weight: 600;
  text-transform: none;
  letter-spacing: 0.5px;
  padding: 0.9rem 1.5rem;
  transition: all 0.4s ease;
  box-shadow: 0 8px 25px rgba(26, 174, 141, 0.4);
}

.modern-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 35px rgba(26, 174, 141, 0.5);
}

.modern-btn:active {
  transform: translateY(-1px);
}

.spinner {
  display: inline-block;
  width: 16px;
  height: 16px;
  border: 2px solid #ffffff50;
  border-radius: 50%;
  border-top-color: #fff;
  animation: spin 1s ease-in-out infinite;
  margin-right: 8px;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

@media (max-width: 768px) {
  .glass-card {
    padding: 2rem !important;
  }
  .icon-wrapper {
    width: 50px;
    height: 50px;
    font-size: 1.2rem;
  }
}
</style>
