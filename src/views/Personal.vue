<template>
  <div class="personal">
    <van-swipe class="my-swipe" :autoplay="3000" indicator-color="white">
      <van-swipe-item
        ><img :src="images[0]" style="width:100%;height:150px"
      /></van-swipe-item>
      <van-swipe-item
        ><img :src="images[0]" style="width:100%;height:150px"
      /></van-swipe-item>
    </van-swipe>
    <div>
      <van-row type="flex" justify="space-between">
        <van-col span="6" class="content">我的预约
        </van-col>
        <van-col span="6" class="content">全部订单
        </van-col>
        <van-col span="6" class="content">实名认证
        </van-col>
      </van-row>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import { Swipe, SwipeItem } from "vant";
Vue.use(Swipe);
Vue.use(SwipeItem);
export default {
  name: "Personal",
  data() {
    return {
      images: [
        "http://file.x-wz.com/image/publicad.png",
        "http://file.x-wz.com/image/publicad.png"
      ]
    };
  },
  components: {}
};
</script>
<style>
.my-swipe .van-swipe-item {
  color: #fff;
  font-size: 20px;
  line-height: 150px;
  text-align: center;
}

.content{
  display:inline-block;
  width:100px;
  height:100px;
  line-height:100px;
  margin:10px;
  color:#1989fa;
  background:#ecf9ff ;
}
</style>
