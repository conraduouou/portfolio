<script setup>
import TheFirst from './TheFirst.vue'
import TheSecond from './TheSecond.vue'
import ContactComponent from '../../components/ContactComponent.vue'
import { onMounted, onUnmounted } from 'vue'

function handleScroll () {
  const scrolled = window.scrollY
  const background = document.getElementById('background')
  background.style.transform = `translateY(${scrolled * 0.15}px)`
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
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
    <TheFirst class="first-section" />
    <span id="works-start"></span>
    <TheSecond id="works" class="second-section" />
    <span id="contact-start"></span>
    <ContactComponent id="contact" />
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
  padding: 0 6vw;
  padding-bottom: 15vh;
}

.first-section {
  padding-top: 20vh;
  margin-bottom: 10vh;
}

.second-section {
  margin-bottom: 10vh;
}

#works-start {
  position: relative;
  top: -20vh;
}

#contact-start {
  position: relative;
  top: -20vh;
}

@media screen and (min-width: 768px) {
  main {
    padding: 0 4vw;
  }
  .first-section {
    padding-top: 25vh;
    margin-bottom: 20vh;
  }

  .circle-1 {
    right: -30%;
    top: 25%;
  }

  .circle-2 {
    left: auto;
    right: -23%;
    top: 64%;
  }

  .circle-3 {
    left: auto;
    right: 10%;
    top: 10%;
  }
}
</style>
