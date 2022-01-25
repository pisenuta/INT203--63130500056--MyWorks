<script setup>
  const headingStyle = "color : blue"
  const paraStyle = "text-decoration: underline"
  const imagePath = "../public/images/mymelody.jfif" //server respose มา
</script>
 
<template>
  <h1 v-bind:style = "headingStyle"> INT203 Web Client II</h1>
  <p :style="paraStyle">lect. Umaporn</p>
  <img src ="./assets/logo.png"> <!--รูปที่เอาไว้ตกแต่ง ไม่ต้องประมวลผลอะไร-->
  <img :src = "imagePath" alt="" srcset=""> <!--รูปที่ต้อง bind ไว้ ต้องรอการประมวลผลก่อนว่าควรขึ้นรูปไหน-->
</template>
  
<style>

</style>

