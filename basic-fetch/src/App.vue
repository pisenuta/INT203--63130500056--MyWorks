<script setup>
  import {ref, onBeforeMount} from 'vue'
  import NoteList from './components/NoteList.vue'
  import CreateEditNote from './components/CreateEditNote.vue'
  const notes = ref([])

  // GET
  const getNotes= async () =>{ //fetch เป็น promise ไม่เสร็จเลยทันที
    //await คือ รอบรรทัดนั้นทำให้เสร็จก่อนแล้วจะทำบรรทัดต่อไป 
    const res = await fetch('http://localhost:5000/notes') //ปกติไม่นิยมวางลิ้งค์
    if(res.status === 200){
      notes.value = await res.json() //json() เป็น promise, get data and เปลี่ยนเป็น js object
      console.log(notes.value)
    } else {
      console.log("error, can not get notes")
    }
    
  }
  onBeforeMount(async () =>{
    await getNotes()
  })

  // DETELE
  const removeNote = async (removeNoteId) =>{
    const res = await fetch(`http://localhost:5000/notes/${removeNoteId}`,{
      method: 'DELETE'
    }) //ชื่อ resource data set และ /id
    if(res.status === 200) {
      notes.value = notes.value.filter((note) => note.id !== removeNoteId)
      console.log('deleted successfullly')
    }
    else console.log('error, can not delete')
  }
  
  // CREATE
  const createNewNote = async (newNote) => {
    const res = await fetch('http://localhost:5000/notes', {
      method: 'POST',
      headers: {
        'content-type': 'application/json' //ระบุ type
      },
      body: JSON.stringify({ noteDetail: newNote }) //stringify คือเปลี่ยน js -> json
    })
    if (res.status === 201) {
      const addedNote = await res.json() //.json คือ ขอข้อมูล
      notes.value.push(addedNote)
      console.log('created successfully')
    } else console.log('error, cannot create')
  }

  // EDIT
  const editingNote = ref({})
  const toEditingMode = (editNote) =>{
    editingNote.value = editNote
    console.log(editingNote.value)
  }
  const modifyNote = async (editingNote) =>{
    const res = await fetch(`http://localhost:5000/notes/${editingNote.id}`,{
      method: 'PUT',
      headers:{
        'content-type': 'application/json'
      },
      body: JSON.stringify({
        noteDetail: editingNote.noteDetail
      })
    })

    if(res.status === 200){
      const modifyNote = await res.json()
      notes.value = notes.value.map((note) => note.id === modifyNote.id? {...note,noteDetail:modifyNote.noteDetail}: note)
      console.log('edited successfully')
    } else {
      console.log('error, cannot edit');
    }
  }
</script>

<template>
  <div>
    <CreateEditNote @createNote="createNewNote" :currentNote="editingNote" @updateNote="modifyNote"/>
    <NoteList 
      :noteList="notes" 
      @deleteNote="removeNote" 
      @editNote="toEditingMode"
    />
  </div>
</template>

<style>

</style>
