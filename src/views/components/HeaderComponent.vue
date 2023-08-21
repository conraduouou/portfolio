<script setup>

function expandOnClick (event) {
  event.stopPropagation()
  const toExpand = document.getElementById('header-items')
  toExpand.classList.toggle('expanded')
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
      <div @click="expandOnClick" class="expand-button">
        <span></span>
        <span></span>
        <span></span>
      </div>
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
  pointer-events: none;
  position: fixed;
  height: 100%;
  width: 100%;
}

header>div:nth-child(1) {
  pointer-events: all;
  display: flex;
  align-items: center;
  width: 100%;
  padding: 4vh 6vw 2.5vh 6vw;
  backdrop-filter: blue(2em);
  -webkit-backdrop-filter: blur(2em);
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

.expand-button {
  height: 1.5em;
  width: 2em;
  margin-left: auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: end;
}

.expand-button span {
  border-bottom: 0.25em solid var(--color-primary);
  border-radius: 1em;
  width: 70%;
  align-self: end;
}

.expand-button span:nth-child(2) {
  align-self: center;
}

.expand-button span:last-child {
  align-self: start;
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
