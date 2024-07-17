<script setup lang="ts">
import { useAttrs, useSlots } from 'vue'
import SlotChild from './SlotChild.vue'
const attrs = useAttrs()
const slots = useSlots()
// 收集全部slots的name
const slotsNames: Array<string> = []
for (const name in slots) {
  slotsNames.push(name)
}
</script>
<template>
  <!-- 透传未消费属性 -->
  <SlotChild v-bind="{ ...attrs }">
    <!-- 透传slots -->
    <template v-for="name in slotsNames" :key="name" #[name]>
      <slot :name="name"></slot>
    </template>
  </SlotChild>
</template>
<style scoped>

</style>

