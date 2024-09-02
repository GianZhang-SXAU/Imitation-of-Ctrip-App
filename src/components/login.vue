<!--
 * @Author: 张建安 337587856@qq.com
 * @Date: 2023-07-12 12:22:34
 * @LastEditors: 张建安 337587856@qq.com
 * @LastEditTime: 2023-07-12 12:22:54
 * @FilePath: \zja-year-two-training\vue-project\src\components\login.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
    <van-nav-bar title="登录"/>
    <!-- 表单 -->
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
          提交
        </van-button>
      </div>
    </van-form>
  </template>
  <script setup>
  import {ref} from "vue";
  
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
      }
    }
  };
  </script>
  <style scoped>
  
  </style>