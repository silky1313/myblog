<template>
  <div class="publish-container">
    <P>请输入你的文章标题</P>
    <el-input v-model="title" size="small" type="textarea" placeholder="Please input your title" />

    <P>请输入文章内容(md文件)</P>
    <el-input
      size="large"
      v-model="mainContext"
      type="textarea"
      placeholder="Please input your mainContext"
      class="article-content"
    />

    <el-button type="primary" plain @click="outerVisible = true">submit your title</el-button>

    <el-dialog v-model="outerVisible" title="是否确认提交？">
      <template #default>
        <el-dialog v-model="innerVisible" width="30%" title="提交成功" append-to-body />
      </template>
      <template #footer>
        <div class="dialog-footer">
          <el-button @click="outerVisible = false">取消提交</el-button>
          <el-button type="primary" @click="submit">确认提交</el-button>
        </div>
      </template>
    </el-dialog>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const textarea1 = ref('');
const mainContext = ref('');
const outerVisible = ref(false);
const innerVisible = ref(false);

function submit() {
  innerVisible.value = true;

  setTimeout(3000);

  innerVisible.value = true;
  outerVisible.value = false;
}
</script>

<style>
.publish-container {
  display: grid;
  gap: 20px;
  margin: 0 auto;
}
.article-content .el-textarea__inner {
  width: 500px;
  height: 300px;
}
</style>