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
  font-weight: 700;
  text-align: center;
  margin-bottom: 0.75rem;
}

p {
  font-weight: 600;
  font-size: 1.25em;
  text-align: center;
}

@media screen and (min-width: 768px) {
  section {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 10vw;
  }

  .section-image {
    height: 40vh;
    width: 40vh;
    margin: 0;
  }

  h2 {
    text-align: left;
  }

  p {
    text-align: left;
  }
}
</style>
