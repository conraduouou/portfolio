<script setup>

function expandOnClick (event) {
  event.stopPropagation()
  const toExpand = document.getElementById('header-items')
  toExpand.classList.toggle('expanded')
}

function onViewWorksClick () {
  window.location.hash = '#/#works'
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
      <a href="#/" class="header-name">Louise Lalu</a>
      <div @click="expandOnClick" class="expand-button">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <div class="header-items-overlay">
      <div id="header-items" class="header-items">
        <a href="#/" class="header-item">Home</a>
        <a href="#/about" class="header-item">About</a>
        <a href="#/#contact" class="header-item">Contact</a>
        <div class="button-container">
          <button @click="onViewWorksClick" type="button" class="header-button">View Works</button>
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
  backdrop-filter: blur(2em);
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

.header-name {
  text-decoration: none;
  color: var(--color-primary);
  font-size: 0.75em;
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

.header-item {
  background-color: var(--color-primary);
  color: var(--color-background);
  padding: 20px 0;
  text-align: center;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.75em;
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
  background-color: var(--color-primary);
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
  font-size: 0.75em;
  font-weight: 600;
  cursor: pointer;
}

.header-button:hover {
  background-color: var(--color-background-dark);
}

@media screen and (min-width: 768px) {
  header {
    display: flex;
    height: auto;
    padding: 4vh 4vw 2.5vh 4vw;
    width: 100%;
    backdrop-filter: blur(2em);
    -webkit-backdrop-filter: blur(2em);
    box-shadow: 0 4px 8px 0 rgba(200, 200, 200, 0.2);
  }

  .header-name {
    font-size: min(1em, 1.5vw);
  }

  header>div:nth-child(1) {
    width: auto;
    padding: 0;
    backdrop-filter: none;
    -webkit-backdrop-filter: none;
    box-shadow: none;
  }

  .header-items-overlay {
    margin-left: auto;
    position: static;
    height: auto;
  }

  .header-items {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 3vw;
    position: static;
    width: auto;
    transition: none;
    transform: none;
  }

  .header-item {
    font-size: min(1em, 1.5vw);
    background-color: transparent;
    color: var(--color-primary);
    padding: 0;
    width: auto;
    border: unset;
  }

  .button-container {
    background-color: transparent;
    display: block;
    padding: 0;
    width: auto;
    border: unset;
  }

  .header-button {
    padding: 1em 0.8em;
    font-size: min(1em, 1.5vw);
    background-color: var(--color-primary);
    color: var(--color-background);
  }

  .header-button:hover {
    background-color: var(--color-primary-600);
  }

  .expand-button {
    display: none;
  }
}
</style>
