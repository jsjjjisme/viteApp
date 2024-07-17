<script setup lang="tsx">
import { useAttrs } from 'vue'
// 获取父组件没有消费的attrs（属性和事件）
const attrs = useAttrs()
</script>
<template>
  <!-- 绑定父组件未消费的属性和事件 -->
  <div @click="attrs.onClick">child</div>
  <div>{{ attrs.date }}</div>
  <div>{{ attrs.time }}</div>
  <slot name="one"></slot>
  <slot name="two"></slot>
</template>
<style scoped></style>
