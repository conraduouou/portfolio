<script setup>
import TheFirst from './TheFirst.vue'
import TheSecond from './TheSecond.vue'
// import TheThird from './TheThird.vue'
import ContactComponent from '../../components/ContactComponent.vue'
</script>

<template>
  <main>
    <TheFirst class="first-section"/>
    <TheSecond/>
    <!-- <TheThird/> -->
    <ContactComponent class="contact-section"/>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  gap: 10vh;
  padding-bottom: 15vh;
}

.first-section {
  padding: 0 6vw;
  padding-top: 20vh;
}

.contact-section {
  margin: 0 6vw;
}

@media screen and (min-width: 768px) {
  .first-section {
    padding: 20vh 4vw 0 10vw;
    height: 80vh;
  }
}
</style>
