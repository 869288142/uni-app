<template>
  <view class="content">
    <view>
      <text class="title" @click="inc()">增加</text>
      <text class="title" @click="dec()">查看</text>
      <text class="title">{{ count }}</text>
    </view>
  </view>
</template>

<script setup lang="ts">
import { useCounter } from '@vueuse/core'
const { count, inc, dec, set, reset } = useCounter()
</script>

<style lang="scss">
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
