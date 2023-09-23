<template>
  <el-card class="box-card">
    <div class="clearfix">
      <span>{{ props.maintitle }}</span>
      <el-button class="button">点击按钮进入文章</el-button>
    </div>
    <div class="text item">
      还不知道再这里写一些什么先写一点点占据一点空间，感觉可以写文章的主要内容
    </div>
  </el-card>
</template>

<script setup>
const props = defineProps(['maintitle']);
console.log(props.maintitle);
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