<script setup>
  const yourName = "Piek"
</script>

<template>
  <!--if yourName = null,0,undefined,NaN,-0 is false -> slide page 11-->
  <p v-show="yourName"> Hello,{{yourName}} </p> 
  <!-- <p v-show="Boolean(yourName)"> Hello,{{yourName}} </p>
      จริงๆ แล้วมี Boolean ครอบไว้ แต่มันซ่อน
  --> 
</template>

<style>

</style>