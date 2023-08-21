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

.contact-section {
  margin: 0 6vw;
}
</style>
