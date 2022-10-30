<template>
  <n-page-header subtitle="让你的听觉更懂视觉" @back="handleBack">
    <template #header>
      <n-menu
        v-model:value="activeKey"
        mode="horizontal"
        :options="menuOptions"
      />
    </template>
    <template #title>
      <a href="/" style="text-decoration: none; color: inherit">zzhhoo</a>
    </template>
    <template #avatar>
      <n-avatar
        src="https://cdnimg103.lizhi.fm/user/2017/02/04/2583325032200238082_160x160.jpg"
      />
    </template>
  </n-page-header>
</template>

<script setup lang="ts">
import { h, ref } from "vue";
import { RouterLink } from "vue-router";
import { useMessage, NAvatar, NMenu, NPageHeader } from "naive-ui";
import type { MenuOption } from "naive-ui";
const message = useMessage();
const activeKey = ref<string | null>(null);
const menuOptions: MenuOption[] = [
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            name: "home",
          },
        },
        { default: () => "主页" }
      ),
    key: "go-back-home",
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            name: "about",
          },
        },
        { default: () => "关于" }
      ),
    key: "go-to-about",
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            name: "chaoshan",
          },
        },
        { default: () => "潮汕词典" }
      ),
    key: "go-to-chaoshan",
  },
];
function handleBack() {
  message.info("[onBack]");
}
</script>
<style scoped>
.n-card {
  max-width: 300px;
}
</style>
