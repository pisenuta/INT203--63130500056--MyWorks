<script setup>
import { ref } from 'vue'
console.clear()
//ใส่ ref เพื่อที่จะให้ค่าใน Template เปลี่ยนแปลงตาม
const counter = ref(1)
//let counter = 1 //มีการแก้ไข setTimeout เลย ใช้ const ไม่ได้
//setTimeout(() => console.log(++counter,3000)) //ใส่ function
setInterval(() => console.log(++counter.value,3000))
//ถ้าใส่ .value ค่าใน template ที่อ้างอิงจาก counter จะเปลี่ยนด้วย
</script>

<template>
 <p>Counter: {{ counter }}</p>
</template>

<style>

</style>
