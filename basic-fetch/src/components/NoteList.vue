<script setup>
    defineEmits(['deleteNote']) //ลงทะเบียน event
    defineProps({
        noteList:{
            type: Array,
            require: true
        }
    })
</script>

<template>
    <div>
        <h2>Note List</h2>
        <ul>
            <li v-for="(note,index) in noteList" :key="index">
                Note Id: {{note.id}},
                Note Detail: {{note.noteDetail}}
                <button @click="$emit('editNote', note)">Edit</button>
                <button @click="$emit('deleteNote',note.id)">Delete</button>
            </li>
        </ul>
    </div>
</template>

<style scoped>

</style>
