<script setup>
const tags = [
  {
    id: 1,
    text: 'flutter'
  },
  {
    id: 2,
    text: 'html/css'
  },
  {
    id: 3,
    text: 'javascript'
  },
  {
    id: 4,
    text: 'vue'
  },
  {
    id: 5,
    text: 'python'
  },
  {
    id: 6,
    text: 'wireframing'
  },
  {
    id: 7,
    text: 'figma'
  },
  {
    id: 8,
    text: 'ui/ux design'
  }
]
</script>

<template>
  <section>
    <div class="section-content">
      <h2>My Career So Far</h2>
      <p>
        Always up for a challenge, I have worked for lean start-ups and was a member of the
        first New Zealand start-up to attend Y Combinator, the largest start-up accelerator in
        the world. From there, I worked my way up to Art Director and Team Lead at Appster where
        I oversaw the design of 30+ mobile and desktop apps. Currently I am a Senior Product
        Designer at LinkTree leading design for the LinkTree mobile app.
      </p>
    </div>
    <div class="section-tags">
      <span class="section-tag" v-for="tag in tags" :key="tag.id"> {{ tag.text }} </span>
    </div>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  background-color: var(--color-primary);
  color: var(--color-background);
  padding: 5vh 6vw 7vh 6vw;
}

h2 {
  font-weight: 600;
  font-size: 2em;
  text-align: center;
  margin-bottom: 1rem;
}

p {
  font-size: min(5vw, 1.25em);
  text-align: center;
  margin-bottom: 2rem;
}

.section-tags {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5em 0.75em;
}

.section-tag {
  text-transform: uppercase;
  font-weight: 600;
  border: 1px solid var(--color-background);
  border-radius: 8px;
  padding: 0.56em;
  padding-bottom: 0.9em;
}

/* section {
  height: var(--section-height);
  display: flex;
  justify-content: space-between;
  gap: max(32px, 6vw);
  align-items: center;
  background-color: var(--color-primary);
  color: var(--color-background);
  padding: var(--section-padding);
}

.section-content {
  width: clamp(360px, 45vw, 560px);
}

.section-content h2 {
  font-weight: 600;
  font-size: 2.5em;
  margin-bottom: 12px;
}

.section-content p {
  font-size: 1.25em;
  line-height: 1.5em;
} */
</style>
