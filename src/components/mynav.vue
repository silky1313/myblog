<template>
  <el-menu
    v-model="activeIndex"
    class="el-menu-demo"
    mode="horizontal"
    :ellipsis="false"
    router="true"
    @select="handleSelect"
  >
    <el-menu-item class="logo" index="1">silky's Blog</el-menu-item>
    <el-menu-item index="1">首页</el-menu-item>
    <el-menu-item index="2">发布新博客</el-menu-item>
  </el-menu>
</template>

<script lang="ts" setup>
import { ref, onMounted, onUnmounted } from 'vue';

const activeIndex = ref('1');
const emit = defineEmits(['changeIndex']);

function handleSelect(index) {
  activeIndex.value = index;
  emit('changeIndex', activeIndex.value);
}
</script>

<style>
.flex-grow {
  flex-grow: 1;
}

.logo {
  font-size: 40px;
}
</style>