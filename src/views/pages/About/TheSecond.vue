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
  },
  {
    id: 9,
    text: 'sql'
  },
  {
    id: 10,
    text: 'php'
  },
  {
    id: 11,
    text: 'postman'
  }
]
</script>

<template>
  <section>
    <div class="section-content">
      <h2>My Career So Far</h2>
      <p>
        Keen for opportunities, I have worked for about any opening I could get. I was exposed to
        software engineering and development during that experience, which instilled in me a drive
        to learn more about the numerous steps included in the whole process, including design,
        backend and a little management. <br><br>
        With that background, I was then able to expand my skills from mobile to desktop and web
        applications.
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

@media screen and (min-width: 768px) {
  section {
    flex-direction: row;
    align-items: center;
    gap: 8vw;
  }

  .section-content {
    flex-shrink: 0;
    width: 53vw;
  }

  h2 {
    text-align: left;
  }

  p {
    text-align: left;
  }

  .section-tags {
    justify-content: start;
  }
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
