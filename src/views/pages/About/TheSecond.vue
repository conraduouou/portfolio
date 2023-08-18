<script setup>
const tags = [
  'ui design', 'ux design', 'prototyping',
  'branding', 'html/css', 'wireframing',
  'information architecture', 'user research',
  'user interviews', 'leadership', 'figma', 'adobe suite'
];
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
      <div class="section-tag" v-for="tag in tags"> {{ tag }} </div>
    </div>
  </section>
</template>

<style scoped>
section {
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
}

.section-tags {
  display: flex;
  flex-wrap: wrap;
  width: clamp(240px, 40vw, 560px);
  gap: 8px 12px;
}

.section-tag {
  text-transform: uppercase;
  font-weight: 600;
  border: 1px solid var(--color-background);
  border-radius: 8px;
  padding: 10px;
  padding-bottom: 14px
}
</style>