<template>
  <div class="bg-white rounded-lg hover:shadow-sm hover:translate-y-[-3px] duration-300">
    <h3 class="border-b border-gray-200 p-2">{{ title }}</h3>
    <p class="border-b border-gray-200 p-2">{{ when }}</p>
    <p class="p-2">{{ description }}</p>

    <section class="flex justify-end">
      <RoundButton label="Register"  @click="$emit('register')" >
        <pre>Register</pre>
      </RoundButton>
    </section>
  </div>
</template>

<script setup>

import RoundButton from '@/components/RoundButton.vue'

defineEmits(['register']);


defineProps({
  title: String,
  when: String,
  description: String,
});

</script>

<style scoped></style>
