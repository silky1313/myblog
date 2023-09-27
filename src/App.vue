<template>
  <div class="main-container">
    <mynav class="main-nav" />
    <!-- 字符串传props可以考虑不使用v-bind 其他的都得使用 -->
    <card
      :class="{ ['suffix-' + index]: true }"
      v-for="(item, index) in maintitle"
      :key="index"
      v-show="item.show"
      :maintitle="item"
      @intoArticle="changeShowArticle(index)"
    ></card>

    <Article clas="main-article" :showArticleIndex="showArtilceIndex"></Article>

    <myinformation class="main-information" />
    <footer class="main-footer">
      hello, this is my footer, there is not important information, please ingore this.
    </footer>
  </div>
</template>

<script setup>
import mynav from './components/mynav.vue';
import card from './components/card.vue';
import myinformation from './components/myinf.vue';
import Article from './components/article.vue';
import { ref } from 'vue';

//show为true代表显示卡片
const maintitle = ref([
  { name: '二维前缀和和差分', show: true },
  { name: '背包dp', show: true },
  {
    name: 'P1967 [NOIP2013 提高组] 货车运输 - 洛谷',
    show: true
  }
]);

let showArtilceIndex = ref(-1);

function changeShowArticle(index) {
  //TODO:首先卡片先都不渲染
  for (let i = 0; i < maintitle.value.length; i++) {
    maintitle.value[i].show = false;
  }

  showArtilceIndex = index;
}
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

.main-article {
  grid-column: 1 / 3;
  grid-row: 2 / -1;
}

.suffix-0 {
  grid-column: 1 / 3;
  grid-row: 2 / 3;
}
.suffix-1 {
  grid-column: 1 / 3;
  grid-row: 3 / 4;
}
.suffix-2 {
  grid-column: 1 / 3;
  grid-row: 4 / 5;
}

.main-information {
  grid-column: 3 / 4;
  grid-row: 2 / 5;
}

.main-footer {
  grid-column: 1 / span 3;
  margin-top: 50px;
  margin: 0 auto;
  grid-row: 6 / 5;
}
</style>



