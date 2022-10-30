<script setup lang="ts">
import { NButton, NResult } from "naive-ui";
</script>

<template>
  <main>
    <n-result status="418" title="我只是个首页" description="一切尽在不言中">
      <template #footer>
        <a href="/chaoshan"><n-button>打开唯一能用的功能</n-button></a>
      </template>
    </n-result>
  </main>
</template>
