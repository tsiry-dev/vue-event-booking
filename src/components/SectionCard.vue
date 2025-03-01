<template>
    <RoundedCard>
      <h3  v-if="$slots.header" class="border-b border-gray-200 p-2">
        <slot name="header"></slot>
      </h3>

      <div v-if="$slots.default" class="border-b border-gray-200 p-2">
        <slot></slot>
      </div>

      <div v-if="$slots.footer" class="p-4">
        <slot name="footer"></slot>
      </div>
    </RoundedCard>
</template>

<script setup>
import RoundedCard from './RoundedCard.vue';

</script>

<style scoped>
</style>
