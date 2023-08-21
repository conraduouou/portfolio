<script setup>
import { ref, computed } from 'vue'
import Header from './views/components/HeaderComponent.vue'
import Footer from './views/components/FooterComponent.vue'
import HomePage from './views/pages/Home/HomePage.vue'
import AboutPage from './views/pages/About/AboutPage.vue'

const routes = {
  '/': HomePage,
  '/about': AboutPage
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
  window.scrollTo(0, 0)
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/']
})
</script>

<template>
  <Header/>
  <component :is="currentView"/>
  <Footer/>
</template>
