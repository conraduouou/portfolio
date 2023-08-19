<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  drawExpand()
})

function expandOnClick (event) {
  event.stopPropagation()
  const toExpand = document.getElementById('header-items')
  toExpand.classList.toggle('expanded')
}

function drawExpand () {
  const width = 300
  const height = 200
  const lineWidth = width * 0.1
  const gap = (height - lineWidth * 3) / 2

  const canvas = document.getElementById('expand')
  const ctx = canvas.getContext('2d')

  canvas.setAttribute('width', width)
  canvas.setAttribute('height', height)

  ctx.strokeStyle = '#de81a4'
  ctx.lineCap = 'round'
  ctx.lineWidth = lineWidth

  for (let i = 0; i < 3; i++) {
    const y = i * ctx.lineWidth + i * gap + ctx.lineWidth / 2
    ctx.moveTo(ctx.lineWidth + i * gap, y)
    ctx.lineTo(width - ctx.lineWidth * 0.67, y)
  }

  ctx.stroke()
}

document.addEventListener('click', (event) => {
  const headerItems = document.getElementById('header-items')
  const clickedElement = event.target

  if (!headerItems.contains(clickedElement)) {
    headerItems.classList.remove('expanded')
  }
})

</script>

<template>
  <header id="header">
    <div>
      <div class="header-logo"></div>
      <h1>Louise Lalu</h1>
      <canvas @click="expandOnClick" id="expand"></canvas>
    </div>
    <div class="header-items-overlay">
      <div id="header-items" class="header-items">
        <span class="header-item">About</span>
        <span class="header-item">Contact</span>
        <div class="button-container">
          <button type="button" class="header-button">View Work</button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
header {
  position: fixed;
  height: 100%;
  width: 100%;
}

header>div:nth-child(1) {
  display: flex;
  align-items: center;
  width: 100%;
  padding: 4vh 6vw 2.5vh 6vw;
  background: var(--color-background);
  box-shadow: 0 4px 8px 0 rgba(200, 200, 200, 0.2);
}

.header-logo {
  height: 2em;
  width: 2em;
  background-color: var(--color-primary);
  margin-right: 1em;
  border-radius: 0.25em;
}

h1 {
  font-size: 1em;
  font-weight: 600;
}

canvas {
  height: 2em;
  width: 3em;
  margin-left: auto;
}

.header-items {
  display: flex;
  flex-direction: column;
  justify-content: start;
  position: absolute;
  pointer-events: all;
  width: 100%;
  transition: transform 0.2s ease-out;
  transform: translateY(-101%);
}

.header-items>* {
  background-color: var(--color-primary);
  color: var(--color-background);
}

.header-item {
  padding: 20px 0;
  text-align: center;
  font-weight: 600;
  width: 100%;
  border-bottom: 1.5px solid var(--color-background);
}

.expanded {
  transform: translateY(0);
}

.header-items-overlay {
  pointer-events: none;
  position: relative;
  overflow: hidden;
  height: 100%;
}

.button-container {
  display: flex;
  justify-content: center;
  padding: 20px 0;
  width: 100%;
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
}

.header-button {
  border: unset;
  padding: 12px 24px;
  background-color: var(--color-background);
  color: var(--color-primary);
  border-radius: 8px;
  transition: background-color 0.2s ease;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
}

.header-button:hover {
  background-color: var(--color-background-dark);
}

@media screen and (min-width: 420px) {
  .header-logo {
    background-color: var(--color-primary);
    height: 24px;
    width: 24px;
    margin-right: 16px;
  }

  h1 {
    font-weight: 600;
    font-size: 16px;
  }

  .header-item {
    font-size: 16px;
    font-weight: 600;
  }
}
</style>
