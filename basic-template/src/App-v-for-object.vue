<script setup>
  const myAccount = {
    accountId: 56,
    accountName: 'urpiek',
    balance: 1000
  }
</script>

<template>
  <ul class="list-disc">
    <!--<li v-for="(value, name) in myAccount">-->
    <li v-for="(value, name, index) in myAccount" :key="index">
      {{index}} - {{name}} : {{value}}
    </li>
  </ul>
</template>

<style>

</style>