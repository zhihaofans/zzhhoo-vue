<script setup>
import { NButton, NInputGroup, NCard, NInput } from "naive-ui";
</script>
<template>
  <n-card title="卡片" hoverable>
    <n-input-group>
      <n-input :style="{ width: '100%' }" />
      <n-button type="primary" ghost> 搜索 </n-button>
    </n-input-group>
  </n-card>
</template>

<style scoped>
.n-card {
  max-width: 3000px;
}
</style>
