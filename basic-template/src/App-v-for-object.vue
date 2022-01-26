<script setup>
  const myAccount = {
    accountId: 56,
    accountName: 'urpiek',
    balance: 1000
  }
</script>

<template>
  <ul class="list-disc">
    <!--<li v-for="(value, propKey) in myAccount">-->
    <li v-for="(value, propKey, index) in myAccount" :key="index">
      {{index}} - {{propKey}} : {{value}}
    </li>
  </ul>
</template>

<style>

</style>