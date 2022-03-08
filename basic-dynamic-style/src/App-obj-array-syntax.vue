<script setup>
const warningColor = 'orange'
const italicText = 'italic'
const isError = false
const warningText = 'color:red'
const successText = 'color:green'
const decorText = 'text-decoration:underline'
const isDecor=true

const dangerText = {color:'red', 'font-style':'italic'}
const dangerText2 = ['color:red', 'font-style:italic']
</script>

<template>
<!-- Style attribute with Obj Syntax -->
<!-- font-style มีขึดขั้นต้องใส่ " " -->
  <p :style="{ color: warningColor, 'font-style': italicText }"> 
    This is style with object syntax 
  </p>
  <p :style="isError?'color:red' : 'color:green'">
    This is erroe message
  </p>
  <p :style="isError? successText : warningText">
    This is binding on varible
  </p>

<!-- Style attribute with Array Syntax -->
  <p :style="[successText,decorText]"> 
    This is style with array syntax 
  </p>
  <p :style="[successText,isDecor? decorText : '']"> 
    This is style on array syntax with condition
  </p>
  <p :style="dangerText">
    danger text
  </p>
  <p :style="[...dangerText2]">
    danger text2
  </p>
</template>

<style>

</style>
