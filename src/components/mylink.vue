<template>
  <div class="container">
    <el-link
      v-for="(item, index) in maincontent"
      :key="index"
      :href="item.content"
      class="link"
      type="primary"
      target="_blank"
    >
      {{ item.name }}
    </el-link>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const maincontent = ref([
      { name: 'github', content: 'https://github.com/silky1313' },
      { name: 'Leetcode', content: 'https://leetcode.cn/u/zero-er/' },
      { name: 'codeforces', content: 'https://codeforces.com/profile/silky' },
      {
        name: 'stackoverflow',
        content: 'https://stackoverflow.com/users/21301988/%e8%b5%b5%e6%af%85%e5%86%9b'
      }
    ]);

    return {
      maincontent
    };
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 50px;
}

.link {
  margin: 10px;
  font-size: 20px;
  border: 1px solid #007bff;
  padding: 5px 10px;
  border-radius: 4px;
  width: 30%;
}
</style>