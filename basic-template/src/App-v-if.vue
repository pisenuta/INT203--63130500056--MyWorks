<script setup>
  const depositAmt = 1000000
  //const interest = 0.1
</script>

<template>
  <p> Deposit Amount : {{ depositAmt }} </p>
  <p v-if="depositAmt < 10000"> Interest : 0 </p>
  <p v-else-if="depositAmt <= 49999"> Interest : {{depositAmt * 0.1}} </p>
  <p v-else-if="depositAmt <= 99999"> Interest : {{depositAmt * 0.2}} </p>
  <p v-else> Interest : {{depositAmt * (interest * 0.25)}}</p>
</template>

<style>

</style>