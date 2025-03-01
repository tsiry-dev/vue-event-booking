<template>
      <button @click="$emit('click')"
      class="border border-gray-200 p-2 rounded-full m-2 hover:bg-gray-100 cursor-pointer">
         <slot></slot>
      </button>
</template>

<script setup>
   defineEmits(['click']);

</script>

<style scoped>
</style>
