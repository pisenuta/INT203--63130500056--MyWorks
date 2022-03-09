<script setup>
defineEmits(['confirm']) //สร้าง custom event
const props = defineProps({
    items:{
        type:Array,
        require:true
    }
})
console.log(props.items);
</script>
 
<template>
<div>
    <ul>
        <li v-for= "(item, index) in items" :key="index">{{item}}</li>
    </ul>
    <div>
        <button @click="$emit('confirm', 'USER_CONFIRM')">Confirm</button>
    </div>
</div>
</template>
 
<style>

</style>