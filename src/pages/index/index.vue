<template>
  <view class="content mt-10">
    <!-- <image class="logo" src="/static/logo.png"></image> -->
    <view class="text-area">
      <text class="title font-mono">Number: {{ counter }}</text>
    </view>
    <button size="mini" type="info" @click="increment">Click Me</button>
    <view class="rounded-xl border-2 border-dark-700 border-solid mt-10">
      <textarea
      class=" border-dark-300"
      v-model="text"
      placeholder="Input something"
      placeholder-class="textarea-placeholder"
      @input=""
    />
    </view>
     <view>{{textSize}}</view>
    <button size="mini" type="primary" class="mt-10" @click="decrement">Navigate To</button>
  </view>
</template>

<script setup>
import { ref, reactive, onMounted, onBeforeMount, onBeforeUnmount, onUnmounted, onActivated, onDeactivated, onReady, onError, onPageScroll, onTabItemTap,computed } from 'vue';

const title = ref('Hello1');

const counter = ref(0);
const textSize = computed(()=>{
  return text.value.length
})
const text = ref('');


const increment = () => {
  counter.value++;
}

const decrement = () => {
  uni.navigateTo({
    url: '/pages/personal/index'
  })
}
</script>

<style lang="scss">

$color: gray;
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: val($color);
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
  margin-bottom: 70rpx;
}

.title {
  font-size: 36rpx;
  color: $color;
}
</style>
