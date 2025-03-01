<template>
  <main class="container mx-auto my-9">
    <h1 class="text-4xl">Event boking App</h1>
    <h2 class="text-3xl text-orange-400 my-5">All events</h2>

    <div class="grid grid-cols-2 gap-5">
      <EventCard v-for="index in 8" :key="index" title="VueConf 2022" when="2022-10-20"
        description="The community that focuses on the future of Vue.js." @register="console.log(index)"  />
    </div>
  </main>
</template>

<script setup>
import EventCard from './components/EventCard.vue';
</script>

<style scoped></style>
