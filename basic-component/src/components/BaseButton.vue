<script setup>
defineEmits(['clickMe']) //เก็บชื่อ custom event
const prop = defineProps({
    buttonName:{
        type:String, //ขึ้นต้นพิมพ์ใหญ่
        require: true
        //default:'OK'
    }
})
console.log(prop.buttonName);
</script>
 
<template>
    <button class="button-color" @click="$emit('clickMe', $event)">{{ buttonName }}</button>
</template>
 
<style scoped>
.button-color{
    background-color: aqua;
}
</style>