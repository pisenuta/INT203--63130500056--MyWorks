<script setup>
  const isSearch = true
</script>

<template>
  <!--true = show , false = hide-->
  <div v-show = "isSearch">
    <label for = "search">Search</label>
    <input type="text" id ="search" class="border">
  </div>
  
</template>

<style>

</style>