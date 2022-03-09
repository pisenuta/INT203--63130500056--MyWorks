<script setup>
import {onUnmounted, onBeforeUnmount} from 'vue'
defineProps({
  currentNum: Number
})
onUnmounted(() => {
  alert(`on unmounted, NumUpdate Component`)
})
onBeforeUnmount(() => {
  alert(`on before unmount, NumUpdate Component`)
})
</script>

<template>
  <div>
    current num: {{currentNum}}
  </div>
</template>

<style scoped>

</style>
