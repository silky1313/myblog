<template>
  <el-card class="box-card">
    <div class="clearfix">
      <span>{{ maintitle.name }}</span>
      <el-button class="button" @click="$emit('intoArticle')">点击按钮进入文章</el-button>
    </div>
    <div class="text item">
      还不知道再这里写一些什么先写一点点占据一点空间，感觉可以写文章的主要内容,建个表，然后有个属性保存文章的主要内容，或者只获取文章的前多少个字渲染即可。
    </div>
  </el-card>
</template>

<script setup>
defineProps(['maintitle']);
</script>

<style>
.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: '';
}
.clearfix:after {
  clear: both;
}

.box-card {
  width: 825px;
}

.button {
  float: right;
}
</style>