<template>
  <div class="main-container">
    <mynav class="main-nav" @changeIndex="handleNavIndexChange" />
    <card
      :class="{ ['suffix-' + index]: true }"
      v-for="(item, index) in maintitle"
      :key="index"
      v-show="item.show && activeIndex == '1'"
      :maintitle="item"
      @intoArticle="changeShowArticle(index)"
    ></card>

    <Article
      class="main-article"
      v-show="showArtilceIndex >= 0 && activeIndex == '1'"
      :showArticleIndex="showArtilceIndex"
      @intocard="changeShowCard()"
    ></Article>

    <publish v-if="activeIndex === '2'"></publish>

    <myinformation class="main-information" />
    <footer class="main-footer">
      hello, this is my footer, there is not important information, please ignore this.
    </footer>
  </div>
</template>

<script setup>
import mynav from './components/mynav.vue';
import card from './components/card.vue';
import myinformation from './components/myinf.vue';
import Article from './components/article.vue';
import publish from './components/publish.vue';
import { ref } from 'vue';

const maintitle = ref([
  { name: '二维前缀和和差分', show: true },
  { name: '背包dp', show: true },
  {
    name: 'P1967 [NOIP2013 提高组] 货车运输 - 洛谷',
    show: true
  }
]);

const showArtilceIndex = ref(-1); // 修改为 const
const activeIndex = ref(1); // 修改为 const

const handleNavIndexChange = (index) => {
  activeIndex.value = index;
  console.log(activeIndex.value);
};

function changeShowArticle(index) {
  for (let i = 0; i < maintitle.value.length; i++) {
    maintitle.value[i].show = false;
  }

  showArtilceIndex.value = index; // 修改为 showArtilceIndex.value
}

function changeShowCard() {
  for (let i = 0; i < maintitle.value.length; i++) {
    maintitle.value[i].show = true;
  }
  showArtilceIndex.value = -1; // 修改为 showArtilceIndex.value
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
  gap: 50px;
}
.main-nav {
  grid-column: 1 / span 3;
  grid-row: 1 / 2;
}

.main-article {
  grid-column: 1 / 3;
  grid-row: 2 / 5;
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