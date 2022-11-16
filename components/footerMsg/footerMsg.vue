<template>
  <view class="centenBox">
    <view class="footerBox">
      <view class="cont">
        <view class="Texts">
          <text @click.stop="openPhone">联系电话：17689758973</text>
          <img @click.stop="openPhone" src="@/static/index_icons/dianhua.png" mode=""></img>
        </view>
        <span class='msg'>版权所有2022 ©版权所有</span>
        <span class='msg'>海南格诺能源科技开发有限公司 </span>
        <span class='msg'>Hainan Geno Energy </span>
        <span class='msg'>Technology Development Co., Ltd </span>
      </view>
    </view>
  </view>
</template>

<script>
  export default {
    name: "footerMsg",
    data() {
      return {}
    },
    methods: {
      //拨打电话
      openPhone() {
        uni.makePhoneCall({
          phoneNumber: '17689758973', //仅为示例 
        });
      },
    }
  }
</script>

<style lang="scss" scoped>
  .centenBox {
    border-top: 10rpx solid #f6f6f6;
    // border: 1rpx solid #ccc;
    box-sizing: border-box;
    width: 100%;
    height: 300rpx;
    background-color: #f6f6f6;
    // border-radius: 15px;
    // border-radius: 15px;
    margin-top: 15rpx;
    padding: 0px 20rpx;

    .footerBox {
      margin-top: 10rpx;
      width: 100%;
      height: 300rpx;
      display: flex;
      box-sizing: border-box;

      .cont {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;

        .Texts {
          color: #000000;
          text-align: center;

          img {
            width: 40rpx;
            height: 40rpx;
          }
        }

        .msg {
          width: 100%;
          text-align: center;
          font-size: 28rpx;
          margin-top: 5rpx;
        }
      }
    }
  }
</style>
