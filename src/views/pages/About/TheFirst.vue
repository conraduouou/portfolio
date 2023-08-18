<script setup>
</script>

<template>
  <section>
    <div class="section-image"></div>
    <div class="section-content">
      <h2>Hi there!</h2>
      <p>
        Fuelled by a passion for designing compelling products, I have a deep desire to
        excel and continuously improve in my work. Learn more about my journey below.
      </p>
    </div>
  </section>
</template>

<style scoped>
section {
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
}

</style>