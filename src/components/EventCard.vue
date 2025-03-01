<template>
    <SectionCard >
     <template #header>
      {{ title }}
     </template>

     {{ when }}

     <template #footer>
       <p class="p-2">{{ description }}</p>

       <div class="flex justify-end">
         <RoundButton label="Register"  @click="$emit('register')" >
           <pre>Register</pre>
         </RoundButton>
       </div>
     </template>
  </SectionCard>
</template>

<script setup>

import RoundButton from '@/components/RoundButton.vue'
 import SectionCard from './SectionCard.vue';



defineProps({
  title: String,
  when: String,
  description: String,
});

defineEmits(['register']);

</script>

<style scoped></style>
