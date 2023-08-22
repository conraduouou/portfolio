<script setup>
import Header from './views/components/HeaderComponent.vue'
import Footer from './views/components/FooterComponent.vue'
import HomePage from './views/pages/Home/HomePage.vue'
import AboutPage from './views/pages/About/AboutPage.vue'
import { shallowRef, computed, nextTick } from 'vue'

const routes = {
  '/': HomePage,
  '/about': AboutPage
}

// make location hash reactive
const hash = shallowRef(window.location.hash)

function scrollToElement (id) {
  const element = document.getElementById(id)

  // if element with the id exists
  if (element) {
    console.log(element)
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

window.addEventListener('hashchange', async () => {
  hash.value = window.location.hash
  const split = hash.value.split('#')

  // if there was an id detected in the hash for navigating to specific sections
  if (split.length >= 3) {
    // await DOM load
    await nextTick()
    scrollToElement(split[2])
  } else {
    // scroll to top as default
    window.scrollTo(0, 0)
  }
})

const currentView = computed(() => {
  const path = hash.value.split('#')[1]
  return routes[path || '/']
})

</script>

<template>
  <Header />
  <component :is="currentView" />
  <Footer />
</template>
