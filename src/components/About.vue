<template>
  <section class="about" id="about">
    <div class="container">
      <div class="mb-5 text-center">
        <h1>À propos de moi</h1>
        <p>Découvrez mon parcours, mes formations et mes expériences.</p>
      </div>

      <div class="row g-4">
        <!-- educ -->
        <div class="col-md-6">
          <div class="glass h-100">
            <h3><i class="fa-solid fa-graduation-cap"></i> Éducation</h3>

            <div class="item">
              <span class="date">2025-2026</span>
              <h5>3ème année Licence - ENI Fianarantsoa</h5>
              <p>Génie Logiciel et Base de Données</p>
            </div>

            <div class="item">
              <span class="date">2024-2025</span>
              <h5>2ème année Licence - ENI Fianarantsoa</h5>
              <p>Génie Logiciel et Base de Données</p>
            </div>

            <div class="item">
              <span class="date">2023-2024</span>
              <h5>1ère année Licence - ENI Fianarantsoa</h5>
              <p>Génie Logiciel et Base de Données</p>
            </div>

            <div class="item">
              <span class="date">2023</span>
              <h5>Baccalauréat</h5>
            </div>
          </div>
        </div>

        <!-- exp -->
        <div class="col-md-6">
          <div class="glass h-100">
            <h3>
              <i class="fa-solid fa-briefcase"></i> Formations & Expériences
            </h3>

            <div class="item">
              <span class="date">24-28 Novembre 2025</span>
              <h5>Formation Robotique</h5>
              <p>ODC Fianarantsoa</p>
            </div>

            <div class="item">
              <span class="date">Septembre – Novembre 2025</span>
              <h5>Gestion des absences et congés</h5>
              <p>Stage - Service Régional du Budget Haute Matsiatra</p>
            </div>

            <div class="item">
              <span class="date">25-29 Novembre 2024</span>
              <h5>Development Web (Vue.js)</h5>
              <p>ODC Antananarivo</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  min-height: 100vh;
  padding: 4rem 1rem;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: white;
}

.glass {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 2rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.item {
  margin-top: 1.5rem;
  padding-left: 1rem;
  border-left: 3px solid #3b82f6;
}

.item h5 {
  margin: 0;
  font-weight: bold;
}

.item p {
  margin: 5px 0;
  font-size: 0.9rem;
  opacity: 0.8;
}

.date {
  font-size: 0.8rem;
  color: #38bdf8;
}

@media (max-width: 768px) {
  .glass {
    margin-bottom: 1rem;
  }
}
</style>
