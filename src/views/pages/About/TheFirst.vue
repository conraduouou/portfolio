<script setup>
</script>

<template>
  <section>
    <div class="section-image"></div>
    <div class="section-content">
      <h2>Hey there!</h2>
      <p>
        Driven by a genuine passion for the harmony of things, development and the world alike,
        I have an innate desire to beat yesterday's me and attain excellence. Check out my journey
        below!
      </p>
    </div>
  </section>
</template>

<style scoped>
section {
  padding: 0 6vw;
  padding-top: 20vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-image {
  border-radius: 0.5em;
  width: min(80%, 400px);
  aspect-ratio: 1 / 1;
  background-color: var(--color-primary);
  margin-bottom: 2em;
}

h2 {
  font-size: 3em;
  font-weight: 600;
  text-align: center;
  margin-bottom: 0.75rem;
}

p {
  font-size: 1.25em;
  text-align: center;
}

/* section {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: var(--section-height);
  padding: var(--section-padding);
}

.section-image {
  height: clamp(400px, 40vh, 600px);
  width: clamp(320px, 32vw, 480px);
  background-color: var(--color-primary);
}

.section-content {
  width: clamp(300px, 40vw, 600px);
}

.section-content h2 {
  font-size: 4em;
  font-weight: 600;
  margin-bottom: 24px;
}

.section-content p {
  font-size: 1.5em;
} */

</style>
