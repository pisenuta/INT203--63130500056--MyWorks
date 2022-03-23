<script setup>
import { useRoute, useRouter } from 'vue-router'
const { params } = useRoute()
console.log(params.studentId)

const myRouter = useRouter()
const goBack = () => myRouter.go(-1) // -1 = go back
const goMyPort = () => myRouter.push({name:'MyPortfolio'}) //ชื่อตามใน index
</script>

<template>
  <div>
    <h1>Student Item</h1>
    <p>your selected student is {{ this.$route.params.studentId }}</p>
    <button @click="goBack">Back</button>
    <button @click="goMyPort">My Portfolio</button>
  </div>
</template>

<style>

</style>