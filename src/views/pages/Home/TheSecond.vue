<script setup>
import WorkItem from '../../components/WorkItem.vue'
</script>

<template>
  <section>
    <h2>Some of my works</h2>
    <div class="work-items">
      <WorkItem class="work-item" :is-mobile=true :asset-url="'/src/views/assets/images/bigbrew.png'">
        This was my first project using Flutter, done for the BigBrew milktea franchise.
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="'/src/views/assets/images/nft.png'">
        This was a side hustle offered to me by my co-worker, done in two (2) weeks!
      </WorkItem>
      <WorkItem class="work-item" :asset-url="'/src/views/assets/images/hospital.png'">
        This was one of my projects in my 2nd year in college which allowed me to be
        proficient in state as well as architecture management in Flutter.
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="'/src/views/assets/images/toolmart.png'">
        This was another of my projects in my 2nd year as well, exploring more performance
        optimizations and animations in Flutter. I also learned how to create an API using
        ASP.NET Core and MongoDB.
      </WorkItem>
      <WorkItem class="work-item" :is-mobile=true :asset-url="'/src/views/assets/images/coffee.png'">
        This was my project for my software engineering subject, which was also done using
        Flutter. By this time, I was exploring more state management options as well as
        implementing API locally using xAMPP.
      </WorkItem>
      <WorkItem class="work-item" :asset-url="'/src/views/assets/images/diligens.png'">
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
  margin-bottom: 1.25em;
}

.work-items {
  display: flex;
  flex-direction: column;
  gap: 3em;
}
</style>
