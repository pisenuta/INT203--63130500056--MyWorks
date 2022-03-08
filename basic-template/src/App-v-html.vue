<script setup>
  const paraStyle = '<i><b>INT203 Web Client II</b></i>'
  const noHTML = '<i><b>INT203 Web Client II</b></i>'
</script>

<template>
  <p v-html="paraStyle"></p>
  <p>{{noHTML}}</p>
</template>

<style>

</style>