<script setup>
import { onMounted, computed } from 'vue'

const props = defineProps({
  isMobile: {
    type: Boolean,
    default: false
  },
  assetUrl: {
    type: String,
    required: true
  }
})

const aspectRatio = computed(() => {
  return props.isMobile ? '7 / 8' : '16 / 9'
})

let workPreviews
onMounted(() => {
  workPreviews = document.querySelectorAll('.work-item')

  window.addEventListener('scroll', checkPreviewsScroll)
  window.addEventListener('load', checkPreviewsScroll)
})

function checkPreviewsScroll () {
  workPreviews.forEach((element) => {
    const elementTop = element.getBoundingClientRect().top
    const windowHeight = window.innerHeight

    // the multiplier for the window height to determine where in the window height should
    // the element be rendered
    const threshold = 0.7

    if (elementTop < windowHeight * threshold) {
      element.classList.add('show')
    }
  })
}
</script>

<template>
  <div class="work-item">
    <div class="work-preview" :style="`--aspect-ratio: ` + aspectRatio  + `; --url: url(` + assetUrl  + `)`"></div>
    <p class="work-description">
      <slot></slot>
    </p>
  </div>
</template>

<style scoped>
.work-item {
  z-index: -1;
  display: flex;
  flex-direction: column;
  opacity: 0;
  transform: translateY(8%);
  transition: opacity 0.2s ease, transform 0.5s ease;
}

.work-preview {
  align-self: center;
  width: min(100%, 400px);
  margin-bottom: 1.25em;
  aspect-ratio: var(--aspect-ratio);
  background-image: var(--url);
  background-size: cover;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
  mask-image: linear-gradient(180deg, #000000 85%, transparent);
}

.show {
  opacity: 1;
  transform: translateY(0);
}

.work-description {
  font-size: 0.92em;
}
</style>
