<template>
  <section>
    <h2>A frontend developer passionate in nailing performant designs to their last detail</h2>
    <p>
      An experienced frontend developer aiming to learn more in various areas such as machine learning,
      data science, and game development.
    </p>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
}

h2 {
  font-size: 2.7em;
  font-weight: 700;
  margin-bottom: 0.75em;
}

p {
  font-weight: 600;
  font-size: 1.2em;
}

@media screen and (min-width: 768px) {
  h2 {
    font-size: 3em;
    width: calc(100vw * 5 / 8);
    margin-bottom: 1rem;
  }

  p {
    width: calc(100vw * 4.3 / 8);
  }
}
</style>
