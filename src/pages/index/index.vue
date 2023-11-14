<template>
  <view class="content">
    <view class="text-area">
      <text class="title" @click="increment">增加</text>
      <text class="title" @click="lookCount">查看</text>
      <text class="title">{{ count }}</text>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";
const count = ref(0);

function increment() {
  count.value = count.value + 1;
  try {
    uni.setStorageSync("storage_key", count.value);
  } catch (e) {
    console.log(e);
    // error
  }
}

function lookCount() {
  try {
    const value = uni.getStorageSync("storage_key");
    if (value) {
      console.log(value);
    }
  } catch (e) {
    console.log(e);
    // error
  }
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
