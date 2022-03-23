<script setup>

</script>

<template>
  <div>
    <div>
      <router-link :to="{ name: 'Home' }">Home</router-link> |
      <router-link :to="{ name: 'MyPortfolio' }">My Portfolio</router-link>
      
    </div>
    <div>
      <router-view> </router-view>
    </div>
  </div>
</template>

<style>
a {
  color: palevioletred;
}

.router-link-active {
  color: rgb(127, 37, 211);
}
</style>
