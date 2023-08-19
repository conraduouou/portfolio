<script setup>
import Header from '../../components/HeaderComponent.vue'
import TheFirst from './TheFirst.vue'
import TheSecond from './TheSecond.vue'
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
      <div class="circle"></div>
    </div>
  </div>

  <Header/>

  <main>
    <TheFirst class="first-section"/>
    <TheSecond class="second-section"/>
  </main>
</template>

<style scoped>
.background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  filter: blur(8em);
  z-index: -1;
}

.circle {
  position: absolute;
  height: 60%;
  width: 60%;
  right: -25%;
  top: -10%;
  background-color: var(--color-secondary);
  border-radius: 50%;
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
