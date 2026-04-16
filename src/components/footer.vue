<template>
  <footer class="footer-section">
    <div class="footer-background"></div>

    <div class="footer-container">
      <h2 class="nom">RAZAFINDRAINIBE Ny Antsafitia Princy</h2>

      <p class="role">Développeur</p>

      <div class="liens">
        <a
          href="https://web.facebook.com/profile.php?id=61576537591892"
          class="lien"
          aria-label="Facebook"
          target="_blank"
        >
          <i class="fab fa-facebook-f"></i>
        </a>

        <a
          href="https://github.com/PrincyRazafy"
          class="lien"
          aria-label="GitHub"
          target="_blank"
        >
          <i class="fab fa-github"></i>
        </a>

        <a
          href="mailto:princyrazafindrainibee@gmail.com"
          class="lien"
          aria-label="Email"
        >
          <i class="fas fa-envelope"></i>
        </a>

        <a
          href="https://www.linkedin.com/in/princy-razafindrainibe-981b3a33a/"
          class="lien"
          aria-label="LinkedIn"
          target="_blank"
        >
          <i class="fab fa-linkedin-in"></i>
        </a>
      </div>

      <div class="ligne"></div>

      <p class="c">&copy; 2026 Princy • Tous droits réservés</p>
    </div>
  </footer>
</template>

<script setup></script>

<style scoped>
.footer-section {
  position: relative;
  background-color: #121212;
  overflow: hidden;
  padding: 40px 20px;
  color: white;
  text-align: center;
}

.footer-background {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(
      circle at 20% 30%,
      rgba(0, 171, 240, 0.25),
      transparent 50%
    ),
    radial-gradient(circle at 80% 70%, rgba(255, 193, 7, 0.2), transparent 50%);
  filter: blur(120px);
  z-index: 0;
}

.footer-container {
  position: relative;
  z-index: 1;
  max-width: 700px;
  margin: auto;
}

.nom {
  font-size: 28px;
  font-weight: 700;
  margin-bottom: 10px;
  letter-spacing: 1px;
}

.role {
  color: #aaa;
  margin-bottom: 25px;
  font-size: 16px;
}

.liens {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 25px;
}

.lien {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 2px solid #00abf0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: white;
  position: relative;
  overflow: hidden;
  transition: 0.4s;
}

.lien::before {
  content: "";
  position: absolute;
  inset: 0;
  background: #00abf0;
  transform: scale(0);
  transition: 0.4s;
  border-radius: 50%;
  z-index: -1;
}

.lien:hover::before {
  transform: scale(1);
}

.lien:hover {
  color: black;
  transform: translateY(-5px) scale(1.1);
}

.ligne {
  height: 1px;
  width: 60%;
  margin: 15px auto;
  background: linear-gradient(to right, transparent, #555, transparent);
}

.c {
  font-size: 14px;
  color: #777;
}
</style>
