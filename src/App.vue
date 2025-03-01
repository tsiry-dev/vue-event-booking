<template>
  <main class="container mx-auto my-9">
    <h1 class="text-4xl">Event boking App</h1>
    <h2 class="text-3xl text-orange-400 my-5">All events</h2>

    <div class="grid grid-cols-2 gap-5" v-if="!eventsLoading">
      <EventCard v-for="event in events"
          :key="event.id"
          :title="event.title"
          :when="event.date"
          :description="event.description"
          @register="handleRegistration(event)"  />

    </div>

    <section v-else>
      <div class="grid grid-cols-2 gap-5">
           <div v-for="index in 6">
              <LoadingEventCard />
           </div>
      </div>
    </section>

    <section>
      <h2 class="text-3xl text-orange-400 my-5">Your Bookings</h2>

      <div class="grid grid-cols-1 gap-4">
        <BookingItem  v-for="index in 3" :key="index"/>
      </div>
    </section>

    <!-- <Box @create="console.log('create')" /> -->
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import BookingItem from './components/BookingItem.vue';
import EventCard from './components/EventCard.vue';
import LoadingEventCard from './components/LoadingEventCard.vue';


const events = ref([]);
const eventsLoading = ref(false);
const eventsLoaded = ref(false);

const fetchEvents = async() => {
  if (eventsLoaded.value) return; // Si les événements sont déjà chargés, on n'envoie pas la requête

  eventsLoading.value = true;
  try{
    const response = await fetch('http://localhost:3001/events');
    events.value = await response.json();

  }finally {
    eventsLoading.value = false;
  }
}

const handleRegistration = async (event) => {
    const newBooking = {
        id: Date.now().toString(),
        userId: 1,
        eventId: event.id,
        evenTitle: event.title
    }

    await fetch('http://localhost:3001/bookings', {
        method: 'POST',
        headers: {
           'Content-Type' : 'application/json'
        },
        body: JSON.stringify({...newBooking, status: 'confirmed'})
    });
}

onMounted(() => fetchEvents());

</script>

<style scoped></style>
