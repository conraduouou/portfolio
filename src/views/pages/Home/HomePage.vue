<script setup>
import TheFirst from './TheFirst.vue'
import TheSecond from './TheSecond.vue'
import ContactComponent from '../../components/ContactComponent.vue'
import { onMounted } from 'vue'

onMounted(() => {
  window.addEventListener('scroll', () => {
    const scrolled = window.scrollY
    const background = document.getElementById('background')
    background.style.transform = `translateY(${scrolled * 0.15}px)`
  })
})

</script>

<template>
  <div class="background-container">
    <div id="background" class="background">
      <div class="circle-1"></div>
      <div class="circle-2"></div>
      <div class="circle-3"></div>
    </div>
  </div>
  <main>
    <TheFirst class="first-section"/>
    <TheSecond class="second-section"/>
    <ContactComponent/>
  </main>
</template>

<style scoped>
.background-container {
  pointer-events: none;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100%;
  height: 100%;
  filter: blur(4em);
}

.background {
  width: 100%;
  height: 100%;
}

.circle-1 {
  position: absolute;
  height: 60vh;
  width: 60vh;
  right: -50%;
  top: -10%;
  background-color: var(--color-secondary);
  opacity: 60%;
  border-radius: 50%;
  transform-origin: 45% 65%;
  animation: 4s linear 0s infinite normal both running special-rotate;
}
.circle-2 {
  position: absolute;
  height: 70vh;
  width: 70vh;
  left: -80%;
  top: 60%;
  background-color: var(--color-neutral);
  border-radius: 50%;
  transform-origin: 40% 35%;
  animation: 8s linear 0s infinite normal both running special-rotate;
}

.circle-3 {
  position: absolute;
  height: 15vh;
  width: 15vh;
  left: 2%;
  top: 10%;
  background-color: var(--color-yellow);
  border-radius: 50%;
  transform-origin: bottom right;
  animation: 8s linear 0s infinite normal both running special-rotate;
}

@keyframes special-rotate {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}

main {
  display: flex;
  flex-direction: column;
  gap: 10vh;
  padding: 0 6vw;
  padding-bottom: 15vh;
}

.first-section {
  padding-top: 20vh;
}
</style>
