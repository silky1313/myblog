<template>
  <div class="article-container">
    <el-button type="primary" plain @click="$emit('intocard')">返回首页</el-button>
    <p v-for="(item, index) in maintitle" :key="index" v-show="showArticleIndex === index">
      <span v-html="renderedMarkdown[index]"></span>
    </p>
  </div>
</template>

<script setup>
import { marked } from 'marked';
import { ref, onMounted } from 'vue';
defineProps(['showArticleIndex']);
const maintitle = ref([
  { name: '二维前缀和和差分.md' },
  { name: '背包dp.md' },
  { name: 'P1967.md' }
]);

const renderedMarkdown = ref([]);

const renderMarkdown = async (filename) => {
  const response = await fetch(`/${filename}`);
  const markdown = await response.text();
  return marked(markdown);
};

onMounted(async () => {
  for (const item of maintitle.value) {
    const markdown = await renderMarkdown(item.name);
    renderedMarkdown.value.push(markdown);
  }
});
</script>

<style scoped>
.article-container {
  font-size: 20px;
  display: grid;
}
/* 根据需要添加样式 */
</style>