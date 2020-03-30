<template>
  <div class="appointment">
    <van-image fit="contain" src="http://file.x-wz.com/image/publicad.png" />

    <van-notice-bar left-icon="volume-o">
      今日预约总计24人：当前排号20号，前方排队人数还剩5人。请耐心等待……
    </van-notice-bar>
    <van-button plain type="info" class="active-num">立即取号</van-button>
    
  </div>
</template>

<script>
import Vue from "vue";
import { NoticeBar } from "vant";
import { Button } from "vant";

Vue.use(NoticeBar);
Vue.use(Button);

export default {
  name: "Appointment",
  components: {}
};
</script>
<style>
.active-num{
    margin-top:50px;
}
</style>
