<script setup>
import { reactive} from 'vue'
console.clear()
const student = reactive({ studentId: 1234, studentName: 'Pleng' })
//reactive ไม่ต้องใช้ .value
console.log(student)
console.log(student.studentName)

const products = reactive(['pepsi', 'coke', 'fanta'])
console.log(products)
console.log(products[1]);

</script>

<template>
<p>student: {{student}}</p>
<p>student id: {{student.studentName}}</p>
</template>

<style>

</style>
