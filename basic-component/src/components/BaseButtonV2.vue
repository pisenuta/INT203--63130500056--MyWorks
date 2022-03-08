<script setup>
import {computed, ref} from 'vue'
const prop=defineProps({
        yourText:{
            type:String,
            require:true
        },
        yourColor:{
            type:String,
            require:true
        }
})
console.log(prop.yourText);
//prop.yourText = 'Confirm' Component BaseButton ไม่มีสิทธิ์แก้ yourText 

//const buttonText =ref(prop.yourText) //Component BaseButton แก้ได้ เพราะมี ref
//buttonText.value = 'Confirm'

//const buttonText =computed(() => prop.yourText) //buttonText เปลี่ยนตาม App.vue
//console.log(buttonText.value);
</script>

<template>
  <!--<button class="button">{{buttonText}}</button>-->
  <button class="button">{{yourText}}</button>
</template>

<style>
.button{
  background-color: v-bind(yourColor);
}
</style>
