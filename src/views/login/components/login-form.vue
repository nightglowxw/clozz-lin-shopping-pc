<template>
  <div>
    <div class="account-box">
      <div class="toggle">
        <a @click="isMsgLogin = false" href="javascrips:;" v-if="isMsgLogin"
          ><i class="iconfont icon-user"></i>使用账号登录</a
        >
        <a @click="isMsgLogin = true" href="javascrips:;" v-else
          ><i class="iconfont icon-msg"></i>使用短信登录</a
        >
      </div>
      <div class="form">
        <template v-if="!isMsgLogin">
          <div class="form-item">
            <div class="input">
              <i class="iconfont icon-user"></i>
              <input type="text" placeholder="请输入用户名" />
            </div>
          </div>
          <div class="form-item">
            <div class="input">
              <i class="iconfont icon-lock"></i>
              <input type="text" placeholder="请输入密码" />
            </div>
          </div>
        </template>
        <template v-else>
          <div class="form-item">
            <div class="input">
              <i class="iconfont icon-user"></i>
              <input type="text" placeholder="请输入手机号" />
            </div>
          </div>
          <div class="form-item">
            <div class="input">
              <i class="iconfont icon-lock"></i>
              <input type="text" placeholder="请输入验证码" />
              <span class="code">发送验证码</span>
            </div>
          </div>
        </template>
        <div class="form-item">
          <div class="agree">
            <input type="radio" name="radio1" value="value1" />
            <span>我已同意</span>
            <a href="javascript:;">《隐私条款》</a>
            <span>和</span>
            <a href="javascript:;">《服务条款》</a>
          </div>
        </div>
        <a href="javascript:;" class="btn">登录</a>
      </div>
      <div class="action">
        <img
          src="https://qzonestyle.gtimg.cn/qzone/vas/opensns/res/img/Connect_logo_7.png"
          alt=""
        />
        <div class="url">
          <a href="javascript:;">忘记密码</a>
          <a href="javascript:;">免费注册</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import {Form, Field} from 'vee-validate'
import { reactive, ref } from 'vue'
export default {
  name: 'login-form',
  setup() {
    //   是否短信登录
    const isMsgLogin = ref(false)

    // 表单信息对象
    const form = reactive({
      isAgree: false
    })

    return {
      isMsgLogin,
      form
    }
  }
}
</script>

<style lang="less" scoped>
.account-box {
  .toggle {
    padding: 15px 40px;
    text-align: right;
    a {
      color: @xtxColor;
      i {
        font-size: 14px;
      }
    }
  }
  .form {
    padding: 0 40px;
    .form-item {
      margin-bottom: 28px;
      .input {
        height: 36px;
        position: relative;
        > i {
          background: #cfcdcd;
          width: 34px;
          height: 34px;
          color: #fff;
          position: absolute;
          left: 1px;
          top: 1px;
          text-align: center;
          line-height: 34px;
          font-size: 18px;
        }
        input {
          padding-left: 44px;
          border: 1px solid #cfcdcd;
          height: 36px;
          line-height: 36px;
          width: 100%;
          &.error {
            border-color: @priceColor;
          }
          &.activ,
          &:focus {
            border-color: @xtxColor;
          }
        }
        .code {
          position: absolute;
          right: 1px;
          top: 1px;
          text-align: center;
          line-height: 34px;
          font-size: 14px;
          background: #f5f5f5;
          color: #666;
          width: 90px;
          height: 34px;
          cursor: pointer;
        }
      }
      > .error {
        position: absolute;
        font-size: 12px;
        line-height: 28px;
        color: @priceColor;
        i {
          font-size: 14px;
          margin-right: 2px;
        }
      }
    }
    .agree {
      input {
        margin-right: 2px;
        line-height: 1;
      }
      a {
        color: #069;
      }
    }
    .btn {
      background: @xtxColor;
      display: block;
      width: 100%;
      height: 40px;
      color: #fff;
      text-align: center;
      line-height: 40px;
      &.disabled {
        background: #cfcdcd;
      }
    }
  }
  .action {
    padding: 20px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .url {
      a {
        color: #999;
        margin-left: 10px;
      }
    }
  }
}
</style>
