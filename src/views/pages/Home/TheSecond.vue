<script setup>
import WorkItem from '../../components/WorkItem.vue'
import { computed } from 'vue'

const basePath = computed(() => {
  let url = window.location.href

  if (url.includes('#')) {
    url = url.split('#')[0]
    url = url.substring(0, url.length - 1)
  }

  return url
})
</script>

<template>
  <section>
    <h2>Some of my works</h2>
    <div class="work-items">
      <WorkItem class="work-item" :is-mobile=true :asset-url="`${basePath}/images/bigbrew.png`">
        This was my first project using Flutter, done for the BigBrew milktea franchise.
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="`${basePath}/images/nft.png`">
        This was a side hustle offered to me by my co-worker, done in two (2) weeks!
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="`${basePath}/images/toolmart.png`">
        This was another of my projects in my 2nd year as well, exploring more performance
        optimizations and animations in Flutter. I also learned how to create an API using
        ASP.NET Core and MongoDB.
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="`${basePath}/images/coffee.png`">
        This was my project for my software engineering subject, which was also done using
        Flutter. By this time, I was exploring more state management options as well as
        implementing API locally using xAMPP.
      </WorkItem>
      <WorkItem class="work-item" :asset-url="`${basePath}/images/hospital.png`">
        This was one of my projects in my 2nd year in college which allowed me to be
        proficient in state as well as architecture management in Flutter.
      </WorkItem>
      <WorkItem class="work-item" :asset-url="`${basePath}/images/diligens.png`">
        This was my first major web development project that pushed me to learn HTML, CSS,
        and JS in-depth. I was also able to implement a simple backend solution for the
        site using PHP.
      </WorkItem>
    </div>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
}

h2 {
  font-weight: 700;
  font-size: 2em;
  margin-bottom: 2.5rem;
}

.work-items {
  display: flex;
  align-self: center;
  width: min(100%, 800px);
  flex-direction: column;
  gap: 3em;
}

@media screen and (min-width: 768px) {
  .work-items {
    display: flex;
    justify-content: center;
    gap: 4.5em 4em;
    flex-wrap: wrap;
    flex-direction: row;
  }
}
</style>
