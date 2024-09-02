<template>
  <!--  首页-->
  <div v-if="active == 0" class="shouye">
    <div v-if="active == 0" class="index">
      <!-- 搜索框 -->
      <van-search v-model="value" placeholder="搜索:目的地/酒店/景点/航班号" shape="round"/>
      <!-- 宫格 -->
      <div class="gridMainDiv">
        <!-- 轮播 -->
        <van-swipe :loop=false class="my-swipe" indicator-color="skyblue" @change="onChange">
          <van-swipe-item>
            <!-- 宫格 -->
            <div class="gridMainDiv">
              <van-grid :border="false">
                <div
                    v-for="value in gridData"
                    :style="{backgroundImage:value.color,backgroundColor:value.color}"
                    class="gridDiv"
                >
                  <van-grid-item :key="value.id" :icon="value.img" :text="value.name"/>
                </div>
              </van-grid>
            </div>
          </van-swipe-item>
          <van-swipe-item :style="{height: height+'px'}">
            <!-- 宫格 -->
            <div class="gridMainDiv">
              <van-grid :border="false">
                <div
                    v-for="value in gridData1"
                    :style="{backgroundImage:value.color,backgroundColor:value.color}"
                    class="gridDiv"
                >
                  <van-grid-item :key="value.id" :icon="value.img" :text="value.name"/>
                </div>
              </van-grid>
            </div>
          </van-swipe-item>
          <template #indicator="{ active, total }">
            <div style="text-align: center;">
              <div :class="active == 0?'swipeIndicatorActive':'swipeIndicatorInactive'"></div>
              <div :class="active == 1?'swipeIndicatorActive':'swipeIndicatorInactive'"></div>
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
                      height="20"
                      src="https://images4.c-ctrip.com/target/0zc71120008g0ha4z93C6.png"
                      width="73"
                  />
                </van-col>
                <van-col span="14" style="text-align: right;">
                  <van-tag color="#ffebe3" size="medium" text-color="#ff4607">特价好货直播中</van-tag>
                </van-col>
              </van-row>
              <div class="swipeDiv">
                <van-swipe :autoplay="3000" class="my-swipe1" indicator-color="white">
                  <van-swipe-item>
                    <div style="height: 130px;background-color: white;">
                      <div
                          style="height: 100px;background-image: url(https://images4.c-ctrip.com/target/0201k120009lh6w07B843_D_280_280_R5.jpg);">
                        <div style="font-size: 10px;color: white;position: absolute;bottom: 0px;margin: 0;padding: 0;">
                          <a>千岛湖明豪国际度假酒店2晚</a>
                        </div>
                      </div>
                      <a style="color: red;font-size: 10px;">￥3699</a>
                    </div>
                  </van-swipe-item>
                  <van-swipe-item>
                    <div style="height: 130px;background-color: white;">
                    <div
                        style="height: 100px;background-image: url(https://images4.c-ctrip.com/target/0201k120009lh6w07B843_D_280_280_R5.jpg);">
                      <div style="font-size: 10px;color: white;position: absolute;bottom: 0px;margin: 0;padding: 0;">
                        <a>千岛湖明豪国际度假酒店2晚</a>
                      </div>
                    </div>
                    <a style="color: red;font-size: 10px;">￥3699</a>
                  </div>
                  </van-swipe-item>
                  <van-swipe-item>
                    <div style="height: 130px;background-color: white;">
                    <div
                        style="height: 100px;background-image: url(https://images4.c-ctrip.com/target/0201k120009lh6w07B843_D_280_280_R5.jpg);">
                      <div style="font-size: 10px;color: white;position: absolute;bottom: 0px;margin: 0;padding: 0;">
                        <a>千岛湖明豪国际度假酒店2晚</a>
                      </div>
                    </div>
                    <a style="color: red;font-size: 10px;">￥3699</a>
                  </div>
                  </van-swipe-item>
                  <van-swipe-item>
                    <div style="height: 130px;background-color: white;">
                    <div
                        style="height: 100px;background-image: url(https://images4.c-ctrip.com/target/0201k120009lh6w07B843_D_280_280_R5.jpg);">
                      <div style="font-size: 10px;color: white;position: absolute;bottom: 0px;margin: 0;padding: 0;">
                        <a>千岛湖明豪国际度假酒店2晚</a>
                      </div>
                    </div>
                    <a style="color: red;font-size: 10px;">￥3699</a>
                  </div>
                  </van-swipe-item>
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
                      height="20"
                      src="https://images4.c-ctrip.com/target/0zc6g120008g0hcb587E5.png"
                      width="73"
                  />
                </van-col>
                <van-col span="14" style="text-align: right;">
                  <van-tag color="#fdefd2" size="medium" text-color="#ae6e15">权威排行榜</van-tag>
                </van-col>
              </van-row>
              <van-row>
                <van-col span="12">
                  <div style="font-size: 15px;">
                    <img alt=""
                         src="https://youimg1.c-ctrip.com/target/0100k120009i7aur9747D_R_238_268.jpg" style="height: 90px;">
                    <van-text-ellipsis :content="text"/>

                  </div>
                </van-col>
                <van-col span="12">
                  <div style="font-size: 15px;">
                    <img alt=""
                         src="https://youimg1.c-ctrip.com/target/0100k120009i7aur9747D_R_238_268.jpg" style="height: 90px;">
                    <van-text-ellipsis :content="text"/>
                  </div>
                </van-col>
              </van-row>
            </div>
          </van-col>
        </van-row>
      </div>
      <!-- 卡片下广告 -->
      <div>
        <div style="display: block;float: initial;margin: 20px 10px 20px 10px;">
          <img src="https://dimg04.c-ctrip.com/images/0zg6z120009hxl5q9CCF7.jpg"
               style="width: 90%; height: 120px; left: 0px; top: 0px; border-radius: 10px; box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 0px 0px;margin-left: 5%;margin-right: auto;"/>
        </div>
      </div>
      <!-- 版权信息 -->
      <div>
        <div style="margin-top: 30px;color: #666;">
          <div style="display: inline;">
            <van-button style="margin-left: 20%;" type="default">
              <van-icon name="phone-o"/>
              电话预定
            </van-button>
            <van-button style="margin-left: 10%;" type="default">
              <van-icon name="down"/>
              下载携程
            </van-button>
          </div>
          <div style="text-align: center;margin-top: 30px;">
            <a>网站地图 | 电脑版</a>

          </div>
          <div style="text-align: center;margin-top: 30px;">
            <a>©2023携程旅行 沪ICP备08023580号</a><br><br><br><br>
          </div>
        </div>
      </div>
    </div>
    <van-sticky style="text-align: right;" :offset-bottom="50" position="bottom">
      <van-image
          width="85"
          height="90"
          src="https://webresource.c-ctrip.com/NFES/html5/1688026760894/_next/serverStatic/img/signin-d.png" />
    </van-sticky>
  </div>


  <div v-if="active == 1" class="community">
    <div v-if="active == 1">

      <!-- van-nav-bar -->
      <van-nav-bar left-text="返回" title="">
        <template #left>
          <van-icon color="rgb(51,51,51)" name="arrow-left" size="21px" @click="onClickLeft"/>
          <div style="color: #222222;font-weight: 700;font-size: 15px;" @click="onClickToPage">全球
            <van-icon color="rgb(51,51,51)" name="arrow-down" size="12px"/>
          </div>
          <!-- 搜索框 -->
          <van-search v-model="value" placeholder="搜索:目的地/景点/话题" shape="round"/>
        </template>
        <template #right>
          <van-image
              height="21px"
              round
              src="https://pages.c-ctrip.com/you/lvpai-home-defaultavat.jpg"
              width="21px"
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
      <van-tabs v-model:active="tabActive" color="#2fcfbb" title-active-color="#222222" title-inactive-color="#222222">
        <van-tab v-for="(value,index) in tabData" :title="value">
          <div v-for="item in myCardData" v-if="tabActive == 0" class="myCard">
            <van-image
                :src="item.img"
                height="253.44"
            />
            <van-text-ellipsis :content="item.title" class="title" rows="2"/>
            <div class="bottom">
              <van-row>
                <van-col span="18">
                  <van-image
                      height="24"
                      round
                      src="https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg"
                      width="24"
                  />
                  <van-text-ellipsis :content="item.username" class="username"/>
                </van-col>
                <van-col span="6">
                  <div class="icon">
                    <van-icon :name="item.userPhoto" size="18"></van-icon>
                  </div>
                  <div class="num">{{ item.num }}</div>
                </van-col>
              </van-row>
            </div>
          </div>
        </van-tab>
      </van-tabs>
      <!-- 发布送积分按钮 -->
      <van-sticky :offset-bottom="50" position="bottom" style="text-align: center;">
        <van-image
            height="90"
            src="https://pages.c-ctrip.com/you/livestream/lvpai_publish_new_btn.png"
            width="85"/>
      </van-sticky>


    </div>
  </div>


  <div v-if="active == 2" class="xiaoxi">
    <van-nav-bar
        left-arrow
        title="消息"
        @click-left="onClickLeft"
    />
    <div
        style="height: 100px;background-color: white;text-align: center;justify-content: center;border-radius: 10px;margin: 15px">
      <van-row>
        <van-col span="6" style="justify-content: center">
          <div style="border-radius: 5px;height: 80px;text-align: center">
            <div style="height: 70px;width: 70px;text-align: center;margin-left: 10px;">
              <img src="https://images4.c-ctrip.com/target/0zc07120008q3qqng006D.png"
                   style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
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
                <img src="https://images4.c-ctrip.com/target/0zc5u120008q3qijiFF72.png"
                     style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
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
                <img src="https://images4.c-ctrip.com/target/0zc3l120008q3q9pf4719.png"
                     style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
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
                <img src="https://dimg04.c-ctrip.com/images/0AS5y120009dnp0ewAB3D.png"
                     style="width: 50px;height: 50px;margin-left: 0px;margin-top: 10px">
                <div>
                  <a>会员服务</a>
                </div>
              </div>
            </div>
          </div>
        </van-col>
      </van-row>
    </div>
    <div v-for="index in Data" style="background-color: white;height: 90px;">
      <van-row>
        <van-col span="4">
          <div style="margin: 10px">
            <van-image
                :src="index.img"
                height="60px"
                round
                width="60px"
            />
          </div>
        </van-col>
        <van-col span="16">
          <div style="margin-left: 10px;margin-top: 10px">
            <a style="font-size: 30px">{{ index.name }}</a><br>
            <a style="color: darkcyan">{{ index.xiaoxi }}</a>
          </div>
        </van-col>
        <van-col span="4" style="padding-top: 5px">
          <a style="color: darkcyan;">{{ index.date }}</a>
        </van-col>
      </van-row>
      <van-divider/>

    </div>
    <div style="text-align: center;margin-top: 10px">
      <a style="color: darkcyan;font-size: 20px">没有更多内容了</a>
    </div>

  </div>


  <div v-if="active == 3" class="wode">
    <div v-if="denglu == 0">
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
            <van-button round type="warning" @click="denglu = 1">登录/注册</van-button>
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
          <van-cell is-link title="常用信息" value="旅客/地址/发票抬头"/>
          <van-cell is-link title="我的收藏" value="降价商品有提醒"/>
          <van-cell is-link title="浏览历史" value="近15天访问记录"/>
          <van-cell is-link title="我要合作" value="供应商加盟/代理合作"/>
        </div>
        <div style="margin-top: 30px">
          <van-cell is-link title="出行工具" value="翻译助手等"/>
        </div>
      </div>
    </div>
    <div v-if="denglu == 1" class="login">
      <van-nav-bar>
        <template #right>
          <a style="color: cornflowerblue;">注册</a>
        </template>
        <template #left>
          <a style="color: cornflowerblue;" @click="onClickLeft1">返回</a>
        </template>
      </van-nav-bar>
      <div style="text-align: center;height: 160px">
        <h2 style="padding-top: 40px;">账号密码登录</h2>
      </div>
      <van-form @submit="onSubmit">
        <van-cell-group inset>
          <van-field
              v-model="username"
              :rules="[{ required: true, message: '请填写用户名' }]"
              label="用户名"
              name="username"
              placeholder="用户名"
          />
          <van-field
              v-model="password"
              :rules="[{ required: true, message: '请填写密码' }]"
              label="密码"
              name="password"
              placeholder="密码"
              type="password"
          />
        </van-cell-group>
        <div style="margin: 16px;">
          <van-button block native-type="submit" round type="primary">
            登录
          </van-button>
        </div>
      </van-form>
      <van-row justify="space-between" style="color: darkcyan">
        <van-col span="6">手机快捷登录</van-col>
        <van-col span="6"></van-col>
        <van-col span="6">境外手机登录</van-col>
      </van-row>
      <div style="font-size: 8px;text-align: center;color: darkcyan;margin-top: 60px;margin-left: 40px">
        <van-radio-group v-model="checked">
          <van-radio name="1">同意携程旅行的<span><a
              href="https://contents.ctrip.com/huodong/privacypolicyh5/index?type=1">《服务协议》</a></span>和<span><a
              href="https://contents.ctrip.com/huodong/privacypolicyh5/index?type=2">《个人隐私保护政策》</a></span>
          </van-radio>
        </van-radio-group>
      </div>
    </div>
  </div>

  <!-- 底部导航栏 -->
  <van-tabbar v-if="!hidden" v-model="active" inactive-color="#666666" @change="onTabBarChange">
    <!-- --van-tabbar-item-text-color 设置导航栏选中的标签的文字颜色 -->
    <van-tabbar-item icon="home-o">首页</van-tabbar-item>
    <van-tabbar-item icon="miniprogram-o">社区</van-tabbar-item>
    <van-tabbar-item icon="chat-o">消息</van-tabbar-item>
    <van-tabbar-item icon="contact">我的</van-tabbar-item>
  </van-tabbar>
</template>
<script setup>
import {ref} from 'vue';


//社区
import {showToast} from 'vant';
import 'vant/es/toast/style';

//登录界面的切换

const denglu = ref(0);
const onClickLeft1 = () => {
  // 返回到首页
  denglu.value = 0
}
const checked = ref('1');
const username = ref('');
const password = ref('');
const onSubmit = (values) => {
  console.log('submit', values);
  // values:
  // {
  //   username:'briup',
  //   password:123,
  // }
  const {username, password} = values
  console.log('🤡 CC - onSubmit - username:', username);
  console.log('🤡 CC - onSubmit - username,password:', username, password);
  if (username == 'zja') {
    if (password == 123321) {
      console.log("登录成功");
      denglu.value = 0
    }
  }
};


// 社区页面的变量以及方法
const myCardData = [
  {
    img: "https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title: "7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username: "红豆带你吃喝玩乐",
    userPhoto: "https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num: "23",
    // 是否点赞
  },
  {
    img: "https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title: "7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username: "红豆带你吃喝玩乐",
    userPhoto: "https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num: "23",
    // 是否点赞
  },
  {
    img: "https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title: "7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username: "红豆带你吃喝玩乐",
    userPhoto: "https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num: "23",
    // 是否点赞
  },
  {
    img: "https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title: "7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username: "红豆带你吃喝玩乐",
    userPhoto: "https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num: "23",
    // 是否点赞
  },
  {
    img: "https://dimg04.c-ctrip.com/images/1me2y12000bml23heAE10_R_640_10000_Q90.jpg?proc=source/tripcommunity",
    title: "7-8月最适合去的旅游地推荐：舒适好玩又避暑！不看后悔",
    username: "红豆带你吃喝玩乐",
    userPhoto: "https://pages.c-ctrip.com/you/livestream/lvpai_detail_commentprise.png",
    num: "23",
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
const tabData = ["发现", "徒步", "避暑", "看海", "玩乐", "酒店", "美食"]


// 底部导航栏的变量
const active = ref(0);
const hidden = ref(false);
const onTabBarChange = (active) => {
  // 当底部导航栏选中 社区、消息、我的时，自动隐藏
  if (active == 0) {
    hidden.value = false
  } else {
    hidden.value = true
  }
}


//聊天数据
const Data = [
  {
    "id": 0,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
  {
    "id": 1,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
  {
    "id": 2,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
  {
    "id": 3,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
  {
    "id": 4,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
  {
    "id": 5,
    "img": "https://fastly.jsdelivr.net/npm/@vant/assets/cat.jpeg",
    "name": "张建安",
    "xiaoxi": "你好，我是张建安",
    "date": "8:30"
  },
]


//首页

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
const gridData1 = [
  {
    id:"1",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/hpgs_guide.png",
    name:"向导/包车",
    color:"#f4f4f4",
  },
  {
    id:"2",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/insurance.png",
    name:"保险",
    color:"#f4f4f4",
  },
  {
    id:"3",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/vtm.png",
    name:"微领队",
    color:"#f4f4f4",
  },
  {
    id:"4",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/oneday.png",
    name:"一日游",
    color:"#f4f4f4",
  },
  {
    id:"5",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/custom.png",
    name:"定制游",
    color:"#f4f4f4",
  },
  {
    id:"6",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/cruise.png",
    name:"游轮",
    color:"#f4f4f4",
  },
  {
    id:"7",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/exchange.png",
    name:"外币兑换",
    color:"#f4f4f4",
  },
  {
    id:"8",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/visa.png",
    name:"签证",
    color:"#f4f4f4",
  },
  {
    id:"9",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/wifi.png",
    name:"WiFi电话卡",
    color:"#f4f4f4",
  },
  {
    id:"10",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/bag.png",
    name:"行李寄送",
    color:"#f4f4f4",
  },
  {
    id:"11",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/lvpai.png",
    name:"旅游跟拍",
    color:"#f4f4f4",
  },
  {
    id:"12",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/flight_schedule.png",
    name:"航班助手",
    color:"#f4f4f4",
  },
  {
    id:"13",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/cost.png",
    name:"拿去花",
    color:"#f4f4f4",
  },
  {
    id:"14",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/gift_card.png",
    name:"礼品卡",
    color:"#f4f4f4",
  },
  {
    id:"15",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/credit_card.png",
    name:"信用卡",
    color:"#f4f4f4",
  },
  {
    id:"16",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/member.png",
    name:"会员/签到",
    color:"#f4f4f4",
  },
  {
    id:"17",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/supermember.png",
    name:"超值旅行家",
    color:"#f4f4f4",
  },
  {
    id:"18",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/rewards.png",
    name:"会员商城",
    color:"#f4f4f4",
  },
  {
    id:"19",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/xiaoshiji.png",
    name:"携程小诗机",
    color:"#f4f4f4",
  },
  {
    id:"20",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/sos.png",
    name:"紧急支援",
    color:"#f4f4f4",
  },
  {
    id:"21",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/cooperation.png",
    name:"加盟合作",
    color:"#ff5f1",
  },
  {
    id:"22",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/mice.png",
    name:"会展旅游",
    color:"#f4f4f4",
  },
  {
    id:"23",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/corpctrip.png",
    name:"企业差旅",
    color:"#f4f4f4",
  },
  {
    id:"24",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/healthy.png",
    name:"核酸检测",
    color:"#f4f4f4",
  },
  {
    id:"25",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/trip.png",
    name:"Trip.com",
    color:"#f4f4f4",
  },
  {
    id:"26",
    img:"https://pic.c-ctrip.com/pic/platform/bbz/h5/h5home/v1/nav/sub/aria.png",
    name:"关怀版",
    color:"#f4f4f4",
  },
]

</script>
<style>
:root {
  /* --van-tabbar-item-active-color:hotpink; */
  --van-field-placeholder-text-color: #999999;
  --van-search-input-height: 30px;
  --van-grid-item-content-background: #00000000;
}


body {
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
:deep(.van-tabbar-item--active > .van-tabbar-item__text) {
  color: #666666
}

//首页
.shouye {
  /* 宫格中遍历的元素div */

  .gridMainDiv {
    margin: 12px;
    border-radius: 10px;
    overflow: hidden;
  }

  .gridDiv {
    width: calc(100% / 5);
    display: inline-block;
  }

  /* :deep(.van-grid){
  } */

  :deep(.van-grid-item__content) {
    height: 58px;
  }

  /* 搜索框 */

  :deep(.van-search__content) {
    border: 1.8px solid #0086f6;
    background: #ffffff;
  }

  :deep(#van-search-1-input) {
    font-size: 15px;
  }

  /* 底部导航栏 */

  :deep(.van-tabbar-item--active > .van-tabbar-item__text) {
    color: #666666
  }

  /* 轮播图的指示器-公共样式 */

  .swipeIndicatorInactive, .swipeIndicatorActive {
    height: 4px;
    border-radius: 2px;
    display: inline-block;
    margin: 0 2px;
  }

  /* 轮播图的指示器-未被选中 */

  .swipeIndicatorInactive {
    width: 4px;
    background-color: #ccc;
  }

  /* 轮播图的指示器被选中 */

  .swipeIndicatorActive {
    width: 14px;
    background-color: #0086f6;
  }

  /* 特价直播div */

  .myDiv {
    width: calc(100% - 28px);
    display: inline-block;
    height: 148px;
    padding: 8px;
    margin-left: 8px;
    border-radius: 8px;
    background: #fff;

    .left, .right {
      // border: 1px solid red;
      // width: calc(50% - 4px);
      height: 20px;
    }

    .left {
      float: left;
      width: 45%;
    }

    .right {
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

}

//社区
:deep(.van-search__content) {
  border: 1.8px solid #0086f6;
  background: #ffffff;
}

//消息页样式
.xiaoxi {

}

//我的页样式
.wode {

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
}


// 社区页样式
.community {
  .myCard {
    display: inline-block;
    width: calc(50% - 15px);
    margin-left: 10px;
    margin-top: 10px;
    border-radius: 6px;
    background-color: #ffffff;
    overflow: hidden;

    .title {
      color: #222222;
      font-size: 14px;
      margin-top: 8px;
      margin-left: 10px;
      width: 178px;
    }

    .bottom {
      margin: 8px 10px 12px 10px;
    }

    .username {
      float: right;
      width: 91.5px;
      height: 24px;
      line-height: 24px;
      color: #333333;
      font-size: 12px;
    }

    .icon {
      float: left;
      padding-top: 3px;
      padding-left: 10px;

    }

    .num {
      color: #222222;
      font-size: 12px;
      float: right;
      height: 24px;
      line-height: 24px;
    }
  }

  :deep(.van-tabs__wrap) {
    margin-bottom: 20px;
  }

  :deep(.van-tab) {
    width: 70px;
  }

  :deep(.van-tab--active) {
    .van-tab__text {
      font-size: 21px;
      font-weight: 400;
    }
  }

  :deep(.van-tab__text) {
    font-size: 16px;
  }

  :deep(.van-search__content) {
    background: #f4f4f4;
  }

  :deep(.van-icon-search) {
    font-size: 14px;
  }

  :deep(.van-search) {
    width: 286px;
  }
}

:deep(#van-search-1-input) {
  font-size: 15px;
}
</style>
