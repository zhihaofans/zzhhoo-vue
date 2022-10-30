<script setup lang="ts">
import {
  NButton,
  NCard,
  NDataTable,
  NInputGroup,
  NInput,
  useMessage,
} from "naive-ui";
import { ref } from "vue";
import dictData from "../../data/chaoshan.json";
const message = useMessage();
const data = ref([
  {
    word: "",
    meaning: "",
  },
]);
const columns = ref([
  {
    title: "词语",
    key: "word",
  },
  {
    title: "意义",
    key: "meaning",
  },
]);
data.value.shift();
const searchKey = ref("");
const inputPlaceholder = ref("输入你想搜索的词");
function search() {
  message.destroyAll();
  if (searchKey.value.length > 0) {
    data.value = dictData.filter(
      (item) =>
        item.word.includes(searchKey.value) ||
        item.meaning.includes(searchKey.value)
    );
    if (data.value.length === 0) {
      inputPlaceholder.value = "找不到你想搜索的关键词";
      message.error("找不到你想搜索的关键词");
    } else {
      inputPlaceholder.value = "输入你想搜索的词";
      message.success("共" + data.value.length + "个结果");
    }
  } else {
    inputPlaceholder.value = "请输入你想搜索的词";
    message.warning("请输入你想搜索的词");
  }
}
</script>
<template>
  <n-card title="潮汕用词搜索" hoverable>
    <n-input-group>
      <n-input
        v-model:value="searchKey"
        :placeholder="inputPlaceholder"
        :style="{ width: '100%' }"
        @enter="search"
      />
      <n-button type="primary" @click="search" ghost> 搜索 </n-button>
    </n-input-group>
    <n-data-table :columns="columns" :data="data" />
  </n-card>
</template>

<style scoped>
.n-card {
  max-width: 1000px;
}
</style>
