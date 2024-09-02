<template>
    <van-nav-bar title="消息" />
  <div style="height: 100px;background-color: white;text-align: center;justify-content: center;border-radius: 10px;margin: 15px">
    <van-row>
      <van-col span="6" style="justify-content: center">
        <div style="border-radius: 5px;height: 80px;text-align: center">
          <div style="height: 70px;width: 70px;text-align: center;margin-left: 10px;">
          <img src="https://images4.c-ctrip.com/target/0zc07120008q3qqng006D.png" style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
            <div>
              <a>订单出行</a>
            </div>
          </div>
        </div>
      </van-col>
      <van-col span="6">
        <div style="border-radius: 5px;height: 80px">
          <div style="border-radius: 5px;height: 80px;text-align: center">
            <div style="height: 70px;width: 70px;text-align: center;margin-left: 10px;">
              <img src="https://images4.c-ctrip.com/target/0zc5u120008q3qijiFF72.png" style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
              <div>
                <a>互动消息</a>
              </div>
            </div>
          </div>
        </div>
      </van-col>
      <van-col span="6">
        <div style="border-radius: 5px;height: 80px">
          <div style="border-radius: 5px;height: 80px;text-align: center">
            <div style="height: 70px;width: 70px;text-align: center;margin-left: 10px;">
              <img src="https://images4.c-ctrip.com/target/0zc3l120008q3q9pf4719.png" style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
              <div>
                <a>账户通知</a>
              </div>
            </div>
          </div>
        </div>
      </van-col>
      <van-col span="6">
        <div style="border-radius: 5px;height: 80px">
          <div style="border-radius: 5px;height: 80px;text-align: center">
            <div style="height: 70px;width: 70px;text-align: center;margin-left: 10px">
              <img src="https://dimg04.c-ctrip.com/images/0AS5y120009dnp0ewAB3D.png" style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
              <div>
              <a>会员服务</a>
              </div>
            </div>
          </div>
        </div>
      </van-col>
    </van-row>
  </div>
<div style="background-color: white;height: 90px;" v-for="index in Data">
  <van-row>
    <van-col span="4">
      <div style="margin: 10px">
      <van-image
          round
          width="60px"
          height="60px"
          :src="index.img"
      />
      </div>
    </van-col>
    <van-col span="16">
      <div style="margin-left: 10px;margin-top: 10px">
      <a style="font-size: 30px">{{index.name}}</a><br>
      <a style="color: darkcyan">{{index.xiaoxi}}</a>
      </div>
    </van-col>
    <van-col span="4">
      <a style="color: darkcyan;">{{index.date}}</a>
    </van-col>
  </van-row>
</div>
  <div style="text-align: center;margin-top: 10px">
    <a style="color: darkcyan;font-size: 20px">没有更多内容了</a>
  </div>
</template>
<script setup>

const Data = [
  {
    "id" : 0,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
  {
    "id" : 1,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
  {
    "id" : 2,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
  {
    "id" : 3,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
  {
    "id" : 4,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
  {
    "id" : 5,
    "img" : "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name" : "张建安",
    "xiaoxi" : "你好，我是张建安",
    "date" : "8:30"
  },
]

</script>

<style scoped>
</style>