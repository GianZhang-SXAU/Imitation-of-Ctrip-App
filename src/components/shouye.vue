<!--
 * @Author: 张建安 337587856@qq.com
 * @Date: 2023-07-12 11:07:44
 * @LastEditors: 张建安 337587856@qq.com
 * @LastEditTime: 2023-07-13 07:10:37
 * @FilePath: \zja-year-two-training\vue-project\src\components\shouye.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <!-- 搜索框 -->
  <van-search v-model="value" placeholder="搜索:目的地/酒店/景点/航班号" shape="round"/>
  <!-- 宫格 -->
  <div class="gridMainDiv">
    <!-- 轮播 -->
    <van-swipe class="my-swipe" :loop=false indicator-color="skyblue" @change="onChange">
      <van-swipe-item>
        <!-- 宫格 -->
        <div class="gridMainDiv">
          <van-grid :border="false">
            <div
                :style="{backgroundImage:value.color,backgroundColor:value.color}"
                v-for="value in gridData"
                class="gridDiv"
            >
              <van-grid-item :key="value.id" :icon="value.img" :text="value.name" />
            </div>
          </van-grid>
        </div>
      </van-swipe-item>
      <van-swipe-item :style="{height: height+'px'}">
        <!-- 宫格 -->
        <div class="gridMainDiv">
          <van-grid :border="false">
            <div
                :style="{backgroundImage:value.color,backgroundColor:value.color}"
                v-for="value in gridData"
                class="gridDiv"
            >
              <van-grid-item :key="value.id" :icon="value.img" :text="value.name" />
            </div>
            <div
                :style="{backgroundImage:value.color,backgroundColor:value.color}"
                v-for="value in gridData"
                class="gridDiv"
            >
              <van-grid-item :key="value.id" :icon="value.img" :text="value.name" />
            </div>
          </van-grid>
        </div>
      </van-swipe-item>
      <template #indicator="{ active, total }">
        <div style="text-align: center;">
          <div :class="active == 0?'swipeIndicatorActive':'swipeIndicatorInactive'"> </div>
          <div :class="active == 1?'swipeIndicatorActive':'swipeIndicatorInactive'"> </div>
        </div>
      </template>
    </van-swipe>
    <van-row>
      <van-col span="12">
        <!-- 特价直播 -->
        <div class="myDiv">
          <van-row>
            <van-col span="10">
              <van-image
                  width="73"
                  height="20"
                  src="https://images4.c-ctrip.com/target/0zc71120008g0ha4z93C6.png"
              />
            </van-col>
            <van-col span="14" style="text-align: right;">
              <van-tag size="medium" color="#ffebe3" text-color="#ff4607" >特价好货直播中</van-tag>
            </van-col>
          </van-row>
          <div class="swipeDiv">
            <van-swipe class="my-swipe1" :autoplay="3000" indicator-color="white">
              <van-swipe-item>
                <div style="height: 130px;background-color: white;">
                <div style="height: 100px;background-image: url(https://images4.c-ctrip.com/target/0201k120009lh6w07B843_D_280_280_R5.jpg);">
                  <div style="font-size: 10px;color: white;position: absolute;bottom: 0px;margin: 0;padding: 0;">
                    <a>千岛湖明豪国际度假酒店2晚</a>
                  </div>
                </div>
                <a style="color: red;font-size: 10px;">￥3699</a>
              </div>
              </van-swipe-item>
              <van-swipe-item>2</van-swipe-item>
              <van-swipe-item>3</van-swipe-item>
              <van-swipe-item>4</van-swipe-item>
            </van-swipe>
          </div>
        </div>
      </van-col>
      <van-col span="12">
        <!-- 携程精选榜 -->
        <div class="myDiv">
          <!-- 布局设计2 -->
          <van-row>
            <van-col span="10">
              <van-image
                  width="73"
                  height="20"
                  src="https://images4.c-ctrip.com/target/0zc6g120008g0hcb587E5.png"
              />
            </van-col>
            <van-col span="14" style="text-align: right;">
              <van-tag size="medium" color="#fdefd2" text-color="#ae6e15" >权威排行榜</van-tag>
            </van-col>
          </van-row>
          <van-row>
            <van-col span="12">
              <div style="font-size: 15px;">
              <img style="height: 90px;" src="https://youimg1.c-ctrip.com/target/0100k120009i7aur9747D_R_238_268.jpg" alt="">
              <van-text-ellipsis :content="text" />
       
              </div>
            </van-col>
            <van-col span="12">
              <div style="font-size: 15px;">
              <img style="height: 90px;" src="https://youimg1.c-ctrip.com/target/0100k120009i7aur9747D_R_238_268.jpg" alt="">
              <van-text-ellipsis :content="text" />
            </div>
            </van-col>
          </van-row>
        </div>
      </van-col>
    </van-row>
  </div>
  <!-- 卡片下广告 -->
  <div>
    <ad/>
  </div>
  <!-- 版权信息 -->
  <div>
    <copyright/>
  </div>
</template>
<script setup>
import {ref} from 'vue';
import copyright from './zhuyeextra/copyright.vue';
import ad from './zhuyeextra/ad.vue';
//省略的文本
const text = '上海周边玩水避暑地榜';

// 首页搜索框
const value = ref('');
//轮播事件
const height = ref('184');
const onChange = (index) => {
  if (index == 1) {
    for (let i = 0; i <= 170; i++) {
      setTimeout(() => {
        height.value++
      }, 1 * i)
    }
  } else {
    for (let i = 0; i <= 170; i++) {
      setTimeout(() => {
        height.value--;
      }, 1 * i)
    }
  }
}



// 首页宫格的数组
const gridData = [
  {
    id: "1",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/hotel.png",
    name: "酒店",
    color: " -webkit-gradient(linear,left top,left bottom,from(#fa5956),to(#fb8650))"
  },
  {
    id: "2",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/flight.png",
    name: "机票",
    color: "-webkit-gradient(linear,left top,left bottom,from(#3c83fa),to(#50b2fa))"
  },
  {
    id: "3",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/train_ticket.png",
    name: "火车票",
    color: " -webkit-gradient(linear,left bottom,left top,from(#66a4ff),to(#5e80ff))"
  },
  {
    id: "4",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/vacation.png",
    name: "旅游",
    color: "-webkit-gradient(linear,left top,left bottom,from(#2fc3b6),to(#52d9b3))"
  },
  {
    id: "5",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/gs.png",
    name: "攻略/景点",
    color: " -webkit-gradient(linear,left bottom,left top,from(#ffa846),color-stop(99%,#ff8939))"
  },
  {
    id: "6",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/hotel_inn.png",
    name: "民宿/客栈",
    color: "#fff5f1"
  },
  {
    id: "7",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/flight_package.png",
    name: "机/酒",
    color: " #eff9ff"
  },
  {
    id: "8",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/bus_ticket.png",
    name: "汽车/船票",
    color: " #f2f5ff"
  },
  {
    id: "9",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/ticket.png",
    name: "门票/活动",
    color: "#ecfcf8"
  },
  {
    id: "10",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/food.png",
    name: "美食",
    color: " #fff9f2"
  },
  {
    id: "11",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/hotel_sale.png",
    name: "特饮/爆款",
    color: "#fff5f1"
  },
  {
    id: "12",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/airport_transfer.png",
    name: "接送机/包车",
    color: "#eff9ff"
  },
  {
    id: "13",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/car.png",
    name: "租车",
    color: " #f2f5ff"
  },
  {
    id: "14",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/weekend.png",
    name: "周边游",
    color: "#ecfcf8"
  },
  {
    id: "15",
    img: "https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/main/shop.png",
    name: "购物/免税",
    color: "#fff9f2"
  },
]

</script>
<style>
:root{
  /* --van-tabbar-item-active-color:hotpink; */
  --van-field-placeholder-text-color:#999999;
  --van-search-input-height:30px;
  --van-grid-item-content-background:#00000000;
}
body{
  background-color: #f4f4f4;
}
/* 轮播样式 */
.my-swipe .van-swipe-item {
  color: #fff;
  font-size: 20px;
  line-height: 150px;
  text-align: center;
  background-color: #ffffff;
}
.my-swipe1 .van-swipe-item {
  color: #fff;
  font-size: 20px;
  line-height: 106px;
  text-align: center;
  background-color: #39a9ed;
}
</style>
<style lang="less" scoped>
/* 宫格中遍历的元素div */
.gridMainDiv{
  margin: 12px;
  border-radius: 10px;
  overflow: hidden;
}
.gridDiv{
  width:calc(100% / 5);
  display: inline-block;
}
/* :deep(.van-grid){
} */
:deep(.van-grid-item__content){
  height: 58px;
}
/* 搜索框 */
:deep(.van-search__content){
  border: 1.8px solid #0086f6;
  background:#ffffff;
}
:deep(#van-search-1-input){
  font-size: 15px;
}
/* 底部导航栏 */
:deep(.van-tabbar-item--active > .van-tabbar-item__text){
  color:#666666
}
/* 轮播图的指示器-公共样式 */
.swipeIndicatorInactive,.swipeIndicatorActive
{
  height: 4px;
  border-radius: 2px;
  display: inline-block;
  margin: 0 2px;
}
/* 轮播图的指示器-未被选中 */
.swipeIndicatorInactive{
  width: 4px;
  background-color: #ccc;
}
/* 轮播图的指示器被选中 */
.swipeIndicatorActive{
  width: 14px;
  background-color: #0086f6;
}
/* 特价直播div */
.myDiv{
  width: calc(100% - 28px);
  display: inline-block;
  height: 148px;
  padding: 8px;
  margin-left: 8px;
  border-radius: 8px;
  background: #fff;
  .left,.right{
    // border: 1px solid red;
    // width: calc(50% - 4px);
    height: 20px;
  }
  .left{
    float: left;
    width: 45%;
  }
  .right{
    float: right;
    text-align: right;
    width: 55%;
  }
  // .swipeDiv{
  //   // border: 1px solid red;
  //   width: 100%;
  //   height: 100%;
  // }
}
</style>
