<script setup>
import { ref } from 'vue';
import BaseButton from './components/BaseButtonV2.vue'
const uText = ref('type your text here !')
const uColor = ref('#000000')
</script>

<template>
  <div>
    <div>Your Text: {{uText}}<input type="text" v-model="uText"/></div>

    <div>Your Color: {{uColor}}<input type="color" v-model="uColor"/></div>
    <BaseButton :yourText = "uText" :yourColor = "uColor"/>
  </div>
</template>

<style>

</style>
