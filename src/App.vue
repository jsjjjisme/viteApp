<script setup lang="ts">
import SlotParent from './components/slots/SlotParent.vue'
function click() {
  const a = 'b'
  console.log(a)
}
</script>

<template>
  <SlotParent date="今天" time="今時" @click="click">
    <template #one>
      <div class="stroke">one</div>
    </template>
    <template #two>
      <div>two</div>
    </template>
  </SlotParent>
</template>

<style scoped>
.stroke {
  font-size: 55px; /* 确保字体大小足够大，以便描边效果明显 */
  -webkit-text-stroke: 1px red; /* Webkit浏览器的前缀 */
}
</style>
