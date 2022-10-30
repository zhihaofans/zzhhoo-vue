<script setup lang="ts">
import { NConfigProvider, NMessageProvider, zhCN, dateZhCN } from "naive-ui";
import { RouterView } from "vue-router";
import TopBar from "./components/TopBar.vue";
</script>
<template>
  <n-config-provider :locale="zhCN" :date-locale="dateZhCN">
    <n-message-provider>
      <header>
        <TopBar />
      </header>
      <body>
        <RouterView />
      </body>
    </n-message-provider>
  </n-config-provider>
</template>
