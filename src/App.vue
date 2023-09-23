<template>
  <div class="main-container">
    <mynav class="main-nav" />
    <card
      :class="{ ['suffix-' + index]: true }"
      v-for="(item, index) in maintitle"
      :key="index"
      :maintitle="item"
    ></card>
    <myinformation class="main-information" />
    <footer class="main-footer">
      京 ICP 证 110745 号 · 京 ICP 备 13052560 号 - 1 · 京公网安备 11010802020088 号 ·
      京网文[2022]2674-081 号 · 药品医疗器械网络信息服务备案（京）网药械信息备字（2022）第00334号 ·
      广播电视节目制作经营许可证:（京）字第06591号 · 服务热线：400-919-0001 · Investor Relations · ©
      2023 知乎 北京智者天下科技有限公司版权所有 · 违法和不良信息举报：010-82716601 ·
      举报邮箱：jubao@zhihu.com
    </footer>
  </div>
</template>

<script setup>
import mynav from './components/mynav.vue';
import card from './components/card.vue';
import myinformation from './components/myinf.vue';
import { ref } from 'vue';

const maintitle = ref(['LCA', 'DP', 'TwoPoint']);
</script>

<style>
.main-container {
  display: grid;
  grid-auto-columns: 1fr 1fr 1fr;
  grid-auto-rows: repeat(5, 1fr);
  width: 1200px;
  /* 设置居中 */
  margin: 0 auto;
  gap: 30px;
}

.main-nav {
  grid-column: 1 / span 3;
  grid-row: 1 / -1;
}

.suffix-0 {
  grid-column: 1 / 2;
  grid-row: 2 / 3;
}
.suffix-1 {
  grid-column: 1 / 2;
  grid-row: 3 / 4;
}
.suffix-2 {
  grid-column: 1 / 2;
  grid-row: 4 / 5;
}

.main-information {
  grid-column: 2 / 3;
  grid-row: 2 / 5;
}

.main-footer {
  grid-column: 1 / span 3;
  margin-top: 50px;
  margin: 0 auto;
  grid-row: 6 / 5;
}
</style>

