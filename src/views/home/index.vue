<template>
  <div class="page-home">
    <div class="home-entry">
      <div class="container">
        <!-- 左侧分类 -->
        <HomeCategory />
      </div>
    </div>
  </div>
</template>

<script>
import HomeCategory from './components/home-category'
export default {
  name: 'PageHome',
  components: { HomeCategory }
}
</script>

<style lang="less" scoped>
.xtx-home-page {
  .hoverShadow();
}
</style>
