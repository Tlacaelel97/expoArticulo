<script setup lang="ts">
import cycleImage from '../figuras/ciclo.png'
</script>

<template>
  <figure class="cycle-figure">
    <img :src="cycleImage" alt="Esquema del ciclo celular." />
    <figcaption>Fig. 2. Esquema del ciclo celular [3].</figcaption>
  </figure>

  <div v-click="1" class="closing-overlay">
    <aside class="closing-card" aria-label="Catástrofe mitótica">
      <p>
        Una <strong>catástrofe mitótica</strong> causada por el mal funcionamiento
        de los puntos de control del ciclo celular puede conducir a la
        <strong>muerte celular</strong> y al desarrollo de
        <strong>células tumorales</strong>.
      </p>
    </aside>
  </div>
</template>

<style scoped>
.cycle-figure {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
}
.cycle-figure img {
  display: block;
  width: 100%;
  height: 300px;
  object-fit: contain;
}
.cycle-figure figcaption {
  margin: 0;
  font-size: 14px;
  line-height: 1.4;
  text-align: center;
}
.closing-overlay {
  position: absolute;
  inset: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 48px;
  background: rgb(2 6 23 / 78%);
  backdrop-filter: blur(4px);
  pointer-events: none;
}
.closing-card {
  box-sizing: border-box;
  width: 100%;
  max-width: 820px;
  padding: 40px;
  border: 2px solid #67e8f9;
  border-top: 7px solid #22d3ee;
  border-radius: 20px;
  background: #f0fdff;
  color: #164e63;
  text-align: center;
  box-shadow: 0 24px 70px rgb(0 0 0 / 45%);
  transition: transform 400ms ease;
}
.closing-card p {
  margin: 0;
  font-size: 30px;
  line-height: 1.5;
}
.closing-card strong { color: #0e7490; }
.slidev-vclick-hidden .closing-card { transform: translateY(16px) scale(0.96); }
</style>
