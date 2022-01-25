<script setup>
const msg = "Hello, Vus.js"
const counter = 1
</script>
 
<template>
  <h1> {{ msg.toLocaleLowerCase() }} </h1>
  <!--<p v-text = "msg"></p>-->
  <p> {{ (counter += 10) }} </p>
</template>
 
<style>

</style>

