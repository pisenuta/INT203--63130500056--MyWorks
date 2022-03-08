<script setup>
import BaseButton from './components/BaseButton.vue'
import BaseButton2 from './components/BaseButton2.vue'
import BaseButton3 from './components/BaseButton3.vue'

console.clear();
const testMe1 = () => console.log("Test Me 1");
const testMe2 = (e) => console.log("Test Me 2", e);
const testMe3 = (e) => console.log("Test Me 3", e);
const testMe4 = (e) => console.log("Test Me 4", e);
const testMe5 = (e, n) => console.log("Test Me 5", e, n);
const testMe6 = (e, n) => console.log("Test Me 6", e, n);

const updateMe1 = (e) => console.log('update me 1', e);
</script>

<template>
  <div>
    <div>
      <button @click="testMe1">Test Me 1</button>
      <button @click="testMe2">Test Me 2</button>

      <button @click="testMe3()">Test Me 3</button>
      <button @click="testMe4($event)">Test Me 4</button>

      <button @click="testMe5($event, 999)">Test Me 5</button>
      <button @click="testMe6(999, $event)">Test Me 6</button>
    </div>
    <div>
      <BaseButton button-name="Click Me1" @clickMe="testMe1"/>
      <BaseButton button-name="Click Me2" @clickMe="testMe2"/>

      <BaseButton button-name="Click Me3" @clickMe="testMe3()"/>
      <BaseButton button-name="Click Me4" @clickMe="testMe4($event)"/>

      <BaseButton button-name="Click Me5" @clickMe="testMe5($event,999)"/>
      <BaseButton button-name="Click Me6" @clickMe="testMe6(999, $event)"/>
    </div>
    <div>
      <BaseButton2 button-name="Like Me1" @likeMe="testMe1"/>
      <BaseButton2 button-name="Like Me2" @likeMe="testMe2"/>

      <BaseButton2 button-name="Like Me3" @likeMe="testMe3()"/>
      <BaseButton2 button-name="Like Me4" @likeMe="testMe4($event)"/>

      <BaseButton2 button-name="Like Me5" @likeMe="testMe5($event,999)"/>
      <BaseButton2 button-name="Like Me6" @likeMe="testMe6(999, $event)"/>
    </div>
    <div>
      <BaseButton3 button-name="Update Me1" @updateMe="updateMe1"/>
      <BaseButton3 button-name="Update Me2" @updateMe="testMe2"/>

      <BaseButton3 button-name="Update Me3" @updateMe="testMe3()"/>
      <BaseButton3 button-name="Update Me4" @updateMe="testMe4($event)"/>

      <BaseButton3 button-name="Update Me5" @updateMe="testMe5($event,999)"/>
      <BaseButton3 button-name="Update Me6" @updateMe="testMe6(999, $event)"/>
    </div>
  </div>
</template>

<style>

</style>
