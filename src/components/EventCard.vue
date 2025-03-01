<template>
  <div class="bg-white rounded-lg hover:shadow-sm hover:translate-y-[-3px] duration-300">
    <h3 class="border-b border-gray-200 p-2">{{ title }}</h3>
    <p class="border-b border-gray-200 p-2">{{ when }}</p>
    <p class="p-2">{{ description }}</p>

    <section class="flex justify-end">
      <button @click="$emit('register')"
        class="border border-gray-200 p-2 rounded-full m-2 hover:bg-gray-100 cursor-pointer">Register</button>
    </section>
  </div>
</template>

<script setup>

defineProps({
  title: String,
  when: String,
  description: String,
});

defineEmits(['register']);
</script>

<style scoped></style>
