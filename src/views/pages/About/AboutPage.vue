<script setup>
import TheFirst from './TheFirst.vue'
import TheSecond from './TheSecond.vue'
// import TheThird from './TheThird.vue'
// import TheFourth from './TheFourth.vue'
</script>

<template>
  <main>
    <TheFirst class="first-section"/>
    <TheSecond/>
    <!-- <TheThird/> -->
    <!-- <TheFourth/> -->
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  gap: 10vh;
  padding: 0 6vw;
  padding-bottom: 15vh;
}
</style>
