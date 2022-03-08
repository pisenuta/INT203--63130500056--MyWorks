<script setup>
import { ref } from 'vue'
const randNumbers = ref([])
// generates random number in range (1-99)
const generateNumber = () => {
  let duplicate = false
  const rand = Math.floor(Math.random() * 99 + 1)
  duplicate = randNumbers.value.some((randNumber) => randNumber === rand)
  duplicate ? generateNumber() : randNumbers.value.push(rand)
  console.log(randNumbers.value);
}
const reset = () => {
  randNumbers = []
}
const student = "63130500056 Thanyakorn Thalaengdi"
</script>

<template>
<p class="style">{{student}}</p>
  <div class="top-container">
    <div class="action-button">
      <button @click="generateNumber">Generate New Number</button>
      <button @click="reset">Reset</button>
    </div>

    <div class="error-message">
      <!-- show error message when a user adding the same number in the bingo sheet -->
    </div>

    <div class="grid-container">
      <div v-for="grid in 9" class="grid-item">
      <!-- show bingo 3 rows x 3 cols here -->
      <p v-if ="randNumbers.length === 0"><button disabled>Add Number</button></p>
      <p v-else><button @click="add">Add Number</button></p>
      </div>
    </div>

    <div class="generate-number">
      <!-- show the list of generated number here -->
      <ul>
        <li v-for="(number,index) in randNumbers" :key="index">
          Generate Number #{{index + 1 }} : '{{number}}'
        </li>
      </ul>
      </div>
  </div>
</template>

<style scoped>
.top-container {
  width: 330px;
}
.action-button {
  padding: 10px;
  display: flex;
  gap: 5px;
}
.grid-container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 80px 80px 80px;
  column-gap: 5px;
  row-gap: 5px;
  background-color: green;
  padding: 10px;
}
.grid-item {
  display: flex;
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  font-size: 30px;
  text-align: center;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.generate-number {
  font-size: 20px;
}
.error-message {
  height: 40px;
  color: red;
}
.style {
  color: hotpink;
  font-weight: bold;
}

</style>

