<template>
  <div class="Login">
    <van-image
      round
      width="6rem"
      height="6rem"
      src="http://file.x-wz.com/image/5G.png"
    />
    <h3>登录</h3>
    <van-form validate-first @failed="onFailed">
      <!-- 通过 pattern 进行正则校验 -->
      <van-field
        v-model="value1"
        name="pattern"
        placeholder="手机号"
        :rules="[{ pattern, message: '请输入6位' }]"
      />
      <!-- 通过 validator 进行函数校验 -->
      <van-field
        v-model="value2"
        name="validator"
        placeholder="密码"
        :rules="[{ validator, message: '请输入11位' }]"
      />
      <!-- 通过 validator 进行异步函数校验 -->
      <van-field
        v-model="value3"
        name="asyncValidator"
        placeholder="验证码"
        :rules="[{ validator: asyncValidator, message: '6位' }]"
      />
      <div style="margin-top:40px;">
        <van-button round block type="info" native-type="submit">
          提交
        </van-button>
      </div>
    </van-form>
    
  </div>
</template>

<script>
import Vue from "vue";
import { Button } from "vant";
import { Col, Row } from "vant";
import { Field } from "vant";
import { Form } from "vant";
import { Toast } from "vant";

import { Image } from "vant";

Vue.use(Image);

Vue.use(Button);
Vue.use(Col);
Vue.use(Row);
Vue.use(Field);
Vue.use(Form);



export default {
  name: "Login",
  data() {
    return {
      value1: "",
      value2: "",
      value3: "",
      pattern: /\d{6}/
    };
  },
  methods: {
    // 校验函数返回 true 表示校验通过，false 表示不通过
    validator(val) {
      return /1\d{10}/.test(val);
    },
    // 异步校验函数返回 Promise
    asyncValidator(val) {
      return new Promise(resolve => {
        Toast.loading("验证中...");

        setTimeout(() => {
          Toast.clear();
          resolve(/\d{6}/.test(val));
        }, 1000);
      });
    },
    onFailed(errorInfo) {
      console.log("failed", errorInfo);
    }
  },
  components: {}
};
</script>
<style>

</style>
