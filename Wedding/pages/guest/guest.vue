<template>
 <view class="content">
  <view class="main">
   <view class="item">
    <input placeholder-class="colorPink" type="text" placeholder="输入您的姓名">
   </view>
   <view class="item">
    <input placeholder-class="colorPink" type="text" placeholder="输入您的手机号">
   </view>
   <view class="item">
    <picker @change="bindPickerChange" :value="index" :range="array">
     <!-- <view class="uni-input">{{array[index]}}</view> -->
     <!-- disabled不加这个属性 到某些端  会弹起键盘  有点反人类 -->
     <input :disabled="true" placeholder-class="colorPink" type="text"
      :placeholder="`参加婚礼的人数:${placeholder}`">
    </picker>
   </view>
   <view class="item">
    <input placeholder-class="colorPink" type="text" placeholder="输入您的祝福语">
   </view>
   <view class="submit">
    <button type="primary">提交</button>
   </view>
  </view>
 </view>
</template>

<script>
 export default {
  data() {
   return {
    title: 'picker',
    array: [],
    index: 0,
    time: '12:01',
    placeholder: '1'
   }
  },
  // 组件创建前
  created() {
   for (let i = 1; i <= 1000; i++) {
    this.array.push(i)
   }
  },
  methods: {
   bindPickerChange(e) {
    this.placeholder = e.detail.value + 1
   },
  }
 }
</script>

<style scoped lang="scss">
 page {
  width: 100%;
  height: 100%;
 }

 .colorPink {
  color: pink;
 }

 .content {
  width: 100%;
  height: 100%;
  background-image: url('../../static/bj_2.png');
  background-size: 100% 100%;

  .main {
   position: absolute;
   bottom: -160rpx;
   left: 50%;
   transform: translate(-50%, -50%);
   width: 80%;

   .submit {
    button {
     background-color: pink;
     border-radius: 30rpx;
     color: #fff;
    }
   }

   .item {
    margin: 20rpx 0;
    display: flex;
    align-items: center;
    height: 80rpx;
    border: 1px solid pink;
    border-radius: 20rpx;

    input {
     margin: 0 20rpx;
    }
   }
  }
 }
</style>