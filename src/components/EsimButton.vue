<script setup>
const props = defineProps({
  color: {
    type: String,
    default: 'violet'
  },
  size: {
    type: String,
  },
})
</script>

<template>
  <button :class="['esim__button',color,size]">
    <slot></slot>
  </button>
</template>

<style scoped>

</style>