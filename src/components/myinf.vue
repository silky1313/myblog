<template>
  <div class="myinf-container">
    <div>
      <el-avatar src="/head.png" class="myinf-head"></el-avatar>
    </div>

    <el-descriptions title="个人信息" :column="3" border>
      <el-descriptions-item
        label="用户名"
        label-class-name="my-label"
        content-class-name="my-content"
        >silky</el-descriptions-item
      >
      <el-descriptions-item label="手机号">1573146397</el-descriptions-item>
      <el-descriptions-item label="居住地">衡阳市</el-descriptions-item>
      <el-descriptions-item label="学校">
        <el-tag size="small">长沙学院</el-tag>
      </el-descriptions-item>
      <el-descriptions-item label="联系地址" :contentStyle="{ 'text-align': 'right' }"
        >湖南省衡阳市</el-descriptions-item
      >
    </el-descriptions>
  </div>
</template>

<script setup>
</script>

<style>
.myinf-container {
  display: grid;
  grid-template-rows: 1fr 1fr;
  gap: 30px;
}
.myinf-head {
  margin-left: 20px;
  width: 75%;
  height: 400px;
}
.my-label {
  background: #e1f3d8;
}

.my-content {
  background: #fde2e2;
}
</style>