<script setup>
const courses = [
  'INT203-Web Client II',
  'INT204-Web Server II',
  'INT209-Devops'
]
</script>

<template>
  <ul class="list-disc">
    <!--กำหนด key ทุกครั้ง ที่มีการใช้ v-for-->
    <li v-for="(course, index) in courses" :key="index">
      #{{ index }}-{{ course }}
    </li>

  </ul>

</template>

<style>

</style>