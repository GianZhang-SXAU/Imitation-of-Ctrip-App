<!--
 * @Author: 张建安 337587856@qq.com
 * @Date: 2023-07-12 11:01:47
 * @LastEditors: 张建安 337587856@qq.com
 * @LastEditTime: 2023-07-13 06:32:50
 * @FilePath: \zja-year-two-training\vue-project\src\components\wode.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div class="top" style="text-align: center;color: white;">
    <van-nav-bar
        left-arrow
        @click-left="onClickLeft"
    >
      <template #right>
        <van-icon name="comment-o" size="18px"/>
      </template>
    </van-nav-bar>
    <div style="font-size: 20px;margin-top: 10px;">
      <a>登录携程，开始旅程</a>
      <div style="margin-top: 20px;">
        <van-button round type="warning">登录/注册</van-button>
        <van-button color="rgba(162,226,227,0.38)" round>手机号查单</van-button>
      </div>
    </div>
    <div>
      <div class="info">
        <div style="float: left;margin-top: 20px;margin-left: 60px">
          <van-icon color="black" name="balance-o" size="20px"/>
          <a class="textinfo">钱包</a>
          <div style="font-size: 10px;color: darkgray;padding-left: 20px;padding-top: 5px">
            <a> 礼品卡 | 现金 | 返现 </a>
          </div>
        </div>
      </div>
      <div class="info">
        <van-row gutter="24" style="text-align: center;margin-bottom: 40px">
          <van-col span="8">
            <div style="margin-top: 15px">
              <van-icon color="black" name="coupon-o" size="20px"/>
              <a style="color: black">优惠劵</a>
            </div>
            <div style="margin-top: 5px">
              <a>领劵</a>
            </div>

          </van-col>
          <van-col span="8">
            <div style="margin-top: 15px">
              <van-icon color="black" name="gift-o" size="20px"/>
              <a style="color: black">积分</a>
            </div>
            <div style="margin-top: 5px">
              <a>兑好礼</a>
            </div>

          </van-col>
          <van-col span="8">
            <div style="margin-top: 15px">
              <van-icon color="black" name="diamond-o" size="20px"/>
              <a style="color: black">拿去花</a>
            </div>
            <div style="margin-top: 5px">
              <a>分期付款</a>
            </div>
          </van-col>
        </van-row>
      </div>
    </div>

  <div style="margin-top: 10px;">
    <van-cell title="常用信息" is-link value="旅客/地址/发票抬头" />
    <van-cell title="我的收藏" is-link value="降价商品有提醒" />
    <van-cell title="浏览历史" is-link value="近15天访问记录" />
    <van-cell title="我要合作" is-link value="供应商加盟/代理合作" />
  </div>
  <div style="margin-top: 30px">
    <van-cell title="出行工具" is-link value="翻译助手等" />
  </div>
  </div>
</template>
<script setup>
const xianshi = 0;
const onClickLeft = () => {
  // 返回到首页
  active.value = 0
  // 显示tabbar
  hidden.value = false
};

</script>
<style scoped>

.top {
  background: #1A67A3 url(//pic.c-ctrip.com/platform/h5/my/home/photo_myctrip@2x_6.22.jpg);
  padding-top: 10px;
  padding-bottom: 100px;
  height: 56px;
}

.top van-icon {
  align-items: start;
  top: 20px;
}

/* 返回图标 */
:deep(.van-nav-bar .van-icon) {
  top: 10px;
  color: white;
  width: 50px;
  height: 50px;
}

:deep(.van-nav-bar) {
  background: #0000;
  color: white;
  border: #0000 1px;
}

:deep(.van-nav-bar__content) {
  background: #0000;
}

:deep(van-badge__wrapper) {
  color: white;
}

.info {
  height: 80px;
  background-color: white;
  border-top: darkcyan solid 1px;
  text-align: left;
  color: darkgray;
}

.info .textinfo {
  color: #2c3e50;
  font-size: 15px;
}

</style>