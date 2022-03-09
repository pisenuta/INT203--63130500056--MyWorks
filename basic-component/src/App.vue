<script setup>
import { ref } from 'vue';
import IconGalaAirplay from './components/icon/IconGalaAirplay.vue'
import ListItems from './components/ListItems.vue'
const projects = [
  {section: 1, group: 1, title: 'Bingo'},
  {section: 2, group: 1, title: 'Tic Tac Toe'},
  {section: 3, group: 1, title: 'Matching Game'}
]
const currentStatus =ref('NONE')
const updateStatus = (status) => (currentStatus.value = status)
</script>

<template>
  <div>
    <IconGalaAirplay/> Home
    <ListItems :items="projects" @confirm="updateStatus"/>
    Current Status: {{currentStatus}}
  </div>
</template>

<style>

</style>
