<script setup>
import {ref} from 'vue'
const suggestion = ref('')
const favColor = ref('')
const agree = ref(false)
const job = ref([])
const food = ref('')
const activities = ref([])
</script>

<template>
<!--text-->
<div>
  suggestion <br>
  <textarea
    v-model = 'suggestion'
    cols = '30'
    rows = '10'
    placeholder="type your suggestion here">
  </textarea>
  <p> {{suggestion}} </p>

  <p>_______________________________</p>
</div>

<!--radio-->
<div>
  <input type="radio" value="RED" v-model="favColor"> 
  <label>Red</label> <br>
  <input type="radio" value="GREEN" v-model="favColor">
  <label>Green</label>
  <p>{{favColor}}</p> <!--show value not label-->

  <p>_______________________________</p>
</div>

<!--checkbox-->
<!--Single-->
<div>
  <input type="checkbox" v-model="agree">
  <label>Agree</label>
  <p>{{agree}}</p>

  <p>-----------------------------------------------</p>
</div>

<!--checkbox-->
<!--Multiple-->
<div>
  <input type="checkbox" value="FRONTEND" v-model="job">
  <label>frontend</label>
  <input type="checkbox" value="BACKEND" v-model="job">
  <label>backend</label>
  <input type="checkbox" value="DEVOPS" v-model="job">
  <label>devops</label>
  <p>{{job}}</p>

  <p>_______________________________</p>
</div>

<!--select-->
<!--Single-->
<div>
  <select v-model="food">
    <option value="PIZZA">Pizza</option>
    <option value="SOUP">Soup</option>
    <option value="PASTA">Pasta</option>
  </select>
  <p>{{food}}</p>

  <p>-----------------------------------------------</p>
</div>

<!--select-->
<!--Multiple-->
<div>
   <select v-model="activities" multiple>
    <option value="SLEEP">Sleep</option>
    <option value="READING">Reading</option>
    <option value="WATCH MOVIES">Watch Movies</option>
  </select>
  <p>{{activities}}</p>

  <p>_______________________________</p>
</div>
</template>

<style>

</style>
