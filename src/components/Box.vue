<template>
  <div class="m-20 bg-yellow-700 p-4">
     <h2>COUNTER</h2>

     <form @submit.prevent="create">
       <input type="text" v-model="txt" class="bg-gray-100">
       <RoundButton variant="test" @click="create">Clear</RoundButton>
     </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import RoundButton from './RoundButton.vue';

defineEmits(['create']);


const data = ref([]);
const txt = ref('');


const create = () => {
  console.log('hi');

    data.value.push({
      id: data.value.length + 1,
      text: txt.value,
    });

    txt.value = '';

    console.log(data.value);

};


</script>

<style scoped>
</style>
