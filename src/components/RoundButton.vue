<template>
      <button type="button" @click="$emit('register')"
      :class="['text-sm p-2 rounded-full m-2 transition-all duration-300 cursor-pointer', variants[variant] ?? variants.default]">
         <slot></slot>
      </button>
</template>

<script setup>

const variants = {
  default: 'border border-gray-200 hover:bg-orange-400 hover:text-white',
  danger: 'bg-red-400 hover:bg-red-500 text-white',
  test: 'bg-green-400 hover:bg-green-500 text-white',
}

  defineProps({
    variant: {
      type: String,
      default: 'default'
    }
  })

  defineEmits(['register']);
</script>

<style scoped>
</style>
