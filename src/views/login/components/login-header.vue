<template>
  <header class="login-header">
    <div class="container">
      <h1 class="logo"><router-link to="/"></router-link></h1>
      <h3 class="sub"><slot /></h3>
      <router-link class="entry" to="/">
        进入网站首页
        <i class="iconfont icon-angle-right"></i>
        <i class="iconfont icon-angle-right"></i>
      </router-link>
    </div>
  </header>
</template>

<script>
export default {}
</script>

<style lang="less" sco boped>
.login-header {
  background: #fff;
  border-bottom: 1px solid #e4e4e4;
  .container {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }
  .logo {
    width: 200px;
    a {
      display: block;
      height: 132px;
      width: 100%;
    }
  }
  .sub {
    flex: 1;
    font-size: 24px;
    font-weight: normal;
    margin-bottom: 38px;
    margin-left: 20px;
    color: #666;
  }
  .entry {
    width: 120px;
    margin-bottom: 38px;
    font-size: 16px;
    i {
      font-size: 14px;
      color: @xtxColor;
      letter-spacing: -5px;
    }
  }
}
</style>
