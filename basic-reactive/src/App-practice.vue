<script setup>
import { computed, ref } from 'vue'
const newNote = ref('')
const notes = ref([])
const keywords = ref('')
const filterNotes = computed(() => (
  notes.value.filter((note) => note.toLowerCase().includes(keywords.value.toLowerCase()))
))
//filter ต้องมี (note) เพื่อแกะที่ note แต่ละรายการ
//notes.value.filter กรอง note ที่ includes keywords
const addNote = () => {
  notes.value.push(newNote.value)
  console.log(notes.value);
  }
//ตรง myNote เป็นชื่ออะไรก็ได้
const colorMe = (myNote) => {
  console.log(myNote);
}
</script>

<template>
<div>
  <div v-show = "notes.length > 0"> <!--จะ show ก็ต่อเมื่อมี note -->
    Filter Notes :
    <input type="text" v-model='keywords'/>
    <ul>
      <li v-for="note in filterNotes">
        {{note}}
        <button @clike="colorMe()">Color Me</button>
      </li>
    </ul>
  </div>
  New Note :
    <input type="text" v-model='newNote'/>
    <button @click="addNote">Add Note</button>
</div>
</template>

<style>

</style>