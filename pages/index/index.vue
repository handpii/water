<template>
  <view class="content">

    <swiper indicator-dots :autoplay="autoplay" :interval="interval">
      <!-- v-for循环遍历数组 c-->
      <swiper-item v-for="(item,index) in swipers" :key="index">
        <image :src="item"></image>
      </swiper-item>
    </swiper>

    <view class="kouhao">
      <view class="big">
        <view class="biglogo">格诺能源</view>
        <P> 追求卓越，改善</P>
        <P class="bigp">水资源</P>
      </view>
      <view class="min">
        致力于污水处理及其再利用
      </view>
    </view>

    <view class="items_icons">
      <view class="item_icons borderright">
        <image :lazy-load="true" @click="click_jishu" :src="require('@/static/index/jishu.png')">
          <p>处理技术</p>
      </view>
      <view class="item_icons borderright">
        <image :lazy-load="true" @click="click_fangfa" :src="require('@/static/index/fangfa.png')">
          <p>处理方法</p>
      </view>
      <view class="item_icons">
        <image :lazy-load="true" @click="click_us" :src="require('@/static/index/us.png')">
          <p>关于我们</p>
      </view>
    </view>








    <view class="activityntroduction" v-for="(item,index) in activity_data" :key="index">
      <image :src="item.imgsrc"></image>
      <view class="detil">
        <h2>{{item.name}}</h2>
        <p> {{item.script_data}}
          <view @click="openactivity_detail(item.id)" style="color: #E43D33;font-size: 26rpx;left:0;text-align:right;">
            更多>
          </view>
        </p>

      </view>
    </view>

    <footerMsg />
  </view>
</template>

<script>
  export default {
    data() {
      return {
        autoplay: true,
        interval: 2000,
        swipers: [
          '/static/index/sw1.png',
          '/static/index/sw2.png',
          '/static/index/sw3.png'
        ],
        activity_data: [{
          name: "生产污水处理",
          script_data: "生产污水指企、事业单位在生产、科研过程中所有排放口向外环境排放的废水量总和。",
          id: 1,
          imgsrc: '/static/index/sc.jpg'
        }, {
          name: "生活污水处理",
          script_data: "生活污水是居民日常生活中排出的废水，主要来源于居住建筑和公共建筑，如住宅、机关、学校、医院、商店、公共场所及工业企业卫生间等。",
          id: 2,
          imgsrc: '/static/index/sh.jpg'
        }]
      }
    },
    onLoad() {

    },
    methods: {
      openactivity_detail(e) {

        uni.navigateTo({
          url: '/pages/index-detail/index-detail?id=' + e
        });
        // console.log(e);
      },
      click_jishu() {
        var url = '../jishu/jishu';
        uni.switchTab({
          url
        })
      },
      click_fangfa() {
        var url = '../fangfa/fangfa';
        uni.switchTab({
          url
        })
      },
      click_us() {
        var url = '../us/us';
        uni.switchTab({
          url
        })
      }
    }
  }
</script>

<style lang="scss">
  page {
    background-color: #f6f6f6;
    margin: 0rpx 20rpx;
  }

  .content {
    width: 94%;
    background-color: #ffffff;
  }

  swiper {
    width: 100%;
    height: 200px;
    // border-radius: 50rpx;

    image {
      width: 100%;
      height: 200px;
      // border-radius: 15px;
    }
  }

  .kouhao {
    border-top: 10rpx solid #f6f6f6;
    padding-top: 50rpx;
    background-color: #fff;
    width: 100%;
    background-image: url("@/static/index/bgimg.jpg");
    background-size: 100% 100%;

    .big {
      font-size: 50rpx;
      font-weight: bold;

      .bigp {
        color: #18aeff;
      }

      .biglogo {
        color: red;
      }
    }

    .min {
      padding-bottom: 30rpx;
    }
  }

  .activityntroduction {
    display: flex;
    width: 100%;
    // background-color: #ffffff;
    // border-radius: 15px;
    // border-top-right-radius: 15px;
    padding-top: 50rpx;
    padding-bottom: 20rpx;
    border-top: 10rpx solid #f5f5f5;
    border-buttom: 10rpx solid #f5f5f5;
    // background-image: url('@/static/index_icons/bg-ac.jpg');

    image {
      flex: 1;
      // border-radius: 50%;
      left: 0px;
      top: 0px;
      width: 150px;
      height: 170px;
      display: block;
    }

    .detil {
      flex: 2;
      // background-color: #ffffff;
      // background-image: url('@/static/index_icons/bg-ac.jpg');

      h2 {
        text-align: center;
      }

      p {
        padding-top: 30rpx;
        text-indent: 2em;
        padding: 20rpx 20rpx;
      }
    }
  }

  .items_icons {
    display: flex;
    align-items: center;
    height: 80px;
    width: 100%;
    background-color: #ffffff;
    // border-radius: 15px;
    // border-bottom-right-radius: 15px;
    // margin-top: 10px;
    border-top: 20rpx solid #f6f6f6;

    .item_icons {
      width: 30%;
      // height: 100%;
      flex: 1;
      text-align: center;

      image {
        width: 40px;
        height: 40px;
      }
    }
  }
</style>
