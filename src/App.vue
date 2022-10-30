<script setup lang="ts">
import { NConfigProvider, zhCN, dateZhCN } from "naive-ui";
import { RouterView } from "vue-router";
import TopBar from "./components/TopBar.vue";
</script>
<template>
  <n-config-provider :locale="zhCN" :date-locale="dateZhCN">
    <header>
      <TopBar />
    </header>
    <body>
      <RouterView />
    </body>
  </n-config-provider>
</template>
