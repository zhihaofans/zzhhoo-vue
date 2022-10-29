<template>
  <n-menu v-model:value="activeKey" mode="horizontal" :options="menuOptions" />
</template>

<script setup lang="ts">
import { h, ref, type Component } from "vue";
import { RouterLink } from "vue-router";
import { NIcon, NMenu } from "naive-ui";
import type { MenuOption } from "naive-ui";
import {
  HomeOutline as HomeIcon,
  PersonOutline as AboutIcon,
} from "@vicons/ionicons5";
function renderIcon(icon: Component) {
  return () => h(NIcon, null, { default: () => h(icon) });
}
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
    icon: renderIcon(HomeIcon),
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
    icon: renderIcon(AboutIcon),
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: "https://chaoshan.netlify.app/",
          },
        },
        { default: () => "潮汕词典" }
      ),
    key: "go-to-chaoshan",
    icon: renderIcon(AboutIcon),
  },
];
</script>
