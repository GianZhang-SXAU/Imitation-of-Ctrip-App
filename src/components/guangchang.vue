<template>

  <!-- van-nav-bar -->
  <van-nav-bar title="" left-text="返回">
    <template #left>
      <van-icon name="arrow-left" @click="onClickLeft" size="21px" color="rgb(51,51,51)"/>
      <div @click="onClickToPage" style="color: #222222;font-weight: 700;font-size: 15px;">全球 <van-icon name="arrow-down" size="12px" color="rgb(51,51,51)"/></div>
      <!-- 搜索框 -->
      <van-search shape="round" v-model="value" placeholder="搜索:目的地/景点/话题" />
    </template>
    <template #right>
      <van-image
          round
          width="21px"
          height="21px"
          src="https://pages.c-ctrip.com/you/lvpai-home-defaultavat.jpg"
      />
    </template>
  </van-nav-bar>
  <!-- 使用布局去做 -->
  <!-- <van-row>
    <van-col span="4">
      <van-icon name="arrow-left" @click="onClickLeft" size="21px" color="rgb(51,51,51)"/>
      <div @click="onClickToPage" style="color: #222222;font-weight: 700;font-size: 15px;">全球 <van-icon name="arrow-down" size="12px" color="rgb(51,51,51)"/></div>
    </van-col>
    <van-col span="16">
      <van-search shape="round" v-model="value" placeholder="搜索:目的地/酒店/景点/航班号" />
    </van-col>
    <van-col span="4">
      <van-image
        round
        width="21px"
        height="21px"
        src="https://pages.c-ctrip.com/you/lvpai-home-defaultavat.jpg"
      />
    </van-col>
  </van-row> -->
  <!-- tab -->
  <van-tabs color="#2fcfbb" title-active-color="#222222" title-inactive-color="#222222" v-model:active="tabActive">
    <van-tab v-for="(value,index) in tabData" :title="value">
      <div v-if="tabActive == 0" class="myCard" v-for="item in myCardData">
        <van-image
            height="253.44"
            :src="item.img"
        />
        <van-text-ellipsis class="title" rows="2" :content="item.title" />
        <div class="bottom">
          <van-row>
            <van-col span="18">
              <van-image
                  round
                  width="24"
                  height="24"
                  src="https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg"
              />
              <van-text-ellipsis class="username" :content="item.username" />
            </van-col>
            <van-col span="6">
              <div class="icon">
                <van-icon size="18" :name="item.userPhoto"></van-icon>
              </div>
              <div class="num">{{ item.num }}</div>
            </van-col>
          </van-row>
        </div>
      </div>
    </van-tab>
  </van-tabs>
  <!-- 发布送积分按钮 -->
  <van-sticky style="text-align: center;" :offset-bottom="50" position="bottom">
    <van-image
        width="85"
        height="90"
        src="https://pages.c-ctrip.com/you/livestream/lvpai_publish_new_btn.png" />
  </van-sticky>

</template>
<script setup>
import { ref } from 'vue';

import { showToast } from 'vant';
import 'vant/es/toast/style';
// 社区页面的变量以及方法
const myCardData=[
  {
    img:"https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title:"7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username:"红豆带你吃喝玩乐",
    userPhoto:"https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num:"23",
    // 是否点赞
  },
  {
    img:"https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title:"7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username:"红豆带你吃喝玩乐",
    userPhoto:"https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num:"23",
    // 是否点赞
  },
  {
    img:"https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title:"7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username:"红豆带你吃喝玩乐",
    userPhoto:"https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num:"23",
    // 是否点赞
  },
  {
    img:"https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title:"7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username:"红豆带你吃喝玩乐",
    userPhoto:"https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num:"23",
    // 是否点赞
  },
  {
    img:"https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title:"7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username:"红豆带你吃喝玩乐",
    userPhoto:"https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num:"23",
    // 是否点赞
  },
]
const onClickLeft = () => {
  // 返回到首页
  active.value = 0
  // 显示tabbar
  hidden.value = false
}
const onClickToPage = () => {
  showToast({
    message: '跳转到全球页',
    position: 'top',
  });
}
const tabActive = ref(0)
const tabData = ["发现","徒步","避暑","看海","玩乐","酒店","美食"]
</script>


<style lang="less" scoped>
:deep(.van-search__content) {
  border: 1.8px solid #0086f6;
  background: #ffffff;
}
// 社区页样式
.community{
  .myCard{
    display: inline-block;
    width: calc(50% - 15px);
    margin-left: 10px;
    margin-top: 10px;
    border-radius: 6px;
    background-color: #ffffff;
    overflow: hidden;
    .title{
      color:#222222;
      font-size: 14px;
      margin-top: 8px;
      margin-left: 10px;
      width: 178px;
    }
    .bottom{
      margin: 8px 10px 12px 10px;
    }
    .username{
      float: right;
      width: 91.5px;
      height: 24px;
      line-height: 24px;
      color: #333333;
      font-size: 12px;
    }
    .icon{
      float: left;
      padding-top: 3px;
      padding-left: 10px;

    }
    .num{
      color: #222222;
      font-size: 12px;
      float: right;
      height: 24px;
      line-height: 24px;
    }
  }
  :deep(.van-tabs__wrap){
    margin-bottom: 20px;
  }
  :deep(.van-tab){
    width: 70px;
  }
  :deep(.van-tab--active){
    .van-tab__text{
      font-size: 21px;
      font-weight:400;
    }
  }
  :deep(.van-tab__text){
    font-size: 16px;
  }
  :deep(.van-search__content){
    background:#f4f4f4;
  }
  :deep(.van-icon-search){
    font-size: 14px;
  }
  :deep(.van-search){
    width: 286px;
  }
}
:deep(#van-search-1-input){
  font-size: 15px;
}
</style>