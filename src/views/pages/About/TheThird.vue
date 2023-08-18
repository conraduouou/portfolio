<script setup>
</script>

<template>
  <section>
    <h2>On Working With Me</h2>
    <div class="section-content">
      <div class="section-client">
        <div class="section-client-picture"></div>
        <span>Lana Kinney</span>
        <span>UX Researcher at AKQA</span>
      </div>
      <p>
        "Sebastian is a guru at all things UX design, consistently producing intuitive, modern, and
        bold designs. He is a natural problem solver in the design space so everyong went to him if
        they were stuck on a feature or flow. He has an arsenal of design skills including animation
        graphic design. Not to mention, Seb was a design team lead, which means he managed a full team
        of both onshore and offshore designs reviewing and providing feedback on all of their designs... 
        Any business would be lucky to have him."
      </p>
    </div>
  </section>
</template>

<style scoped>
section {
  height: clamp(480px, 55svh, 720px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: var(--section-padding);
}

section > h2 {
  font-weight: 600;
  font-size: 3em;
  margin-bottom: 28px;
  text-align: center;
}

.section-content {
  display: flex;
  justify-content: space-between;
  gap: max(24px, 8vw);
}

.section-client {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  gap: 14px;
}

.section-client span {
  text-align: center;
}

.section-client span:nth-child(2) {
  font-size: 1.2em;
  font-weight: 600;
}

.section-client-picture {
  border-radius: 50%;
  width: min(120px, 15vw);
  height: min(120px, 15vw);
  background-color: var(--color-primary);
}

.section-content p {
  flex-shrink: 0;
  font-size: 1.25em;
  line-height: 1.5em;
  width: min(800px, 60vw);
}
</style>