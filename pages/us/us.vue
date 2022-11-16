<template>
  <view class="userinfo">
    <view class="tableinformation">
      <view class="tableinformation_img"></view>
      <image :src="userinfo_img"></image>
      <view class="tableinformation_name">
        <p></p>
        <p></p>
        <P>用户名：{{userinfo_name}}</P>
        <p></p>
      </view>
    </view>

    <button class="el-button" type="default" v-on:click="dianji()" v-if="userinfo_img ===''">一键登录</button>



    <view class="">


      <view class="title">
        海南格诺能源科技开发有限公司
      </view>
      <p class="titlep">
        污水处理及其再生利用；地震服务；云计算装备技术服务；地质勘查技术服务；石油天然气技术服务；信息技术咨询服务；数字内容制作服务（不含出版发行）；工程和技术研究和试验发展；新兴能源技术研发；人工智能双创服务平台；环保咨询服务；技术服务、技术开发、技术咨询、技术交流、技术转让、技术推广（除许可业务外，可自主依法经营法律法规非禁止或限制的项目）
      </p>
    </view>

    <view class="buttomanniu">
      <button class="el-button el-buttonkefu" open-type="contact">客服</button>
      <button class="el-button el-buttonzf" open-type="share">转发</button>
      <button class="el-button el-buttonfk" open-type="feedback">意见反馈</button>
    </view>





    <view class="aboutColor">
      <h1>联系我们 </h1>
      <view class="">
        <p>电话：17689758973 </p>
        <p> 邮箱：17689758973@gmail.com</p>
        <p>地址：海南省三亚市吉阳区凤凰路中信南航大厦824</p>
        <view>
          <view class="page-body">
            <view class="page-section page-section-gap">
              <map style="width: 100%; height: 200px;" :latitude="latitude" :longitude="longitude" :markers="covers">
              </map>
            </view>
          </view>
        </view>
      </view>
    </view>

    <!-- 底部组件 -->
    <footerMsg />

  </view>

</template>

<script>
  export default {
    data() {
      return {
        userinfo_img: '',
        userinfo_name: "游客",

        id: 1, // 使用 marker点击事件 需要填写id
        title: 'map',
        latitude: 18.274908,
        longitude: 109.514343,
        covers: [{
          width: 30,
          height: 30,
          latitude: 18.274908,
          longitude: 109.514343,
          iconPath: '../../static/us/location.png'
        }, {
          width: 30,
          height: 30,
          latitude: 18.274908,
          longitude: 109.514343,
          iconPath: '../../static/us/location.png'
        }]

      };
    },
    onLoad() {
      // this.getuser()

    },
    methods: {
      dianji() {
        let that = this;
        uni.getUserProfile({
          desc: '用于完善用户资料',
          success(e) {

            console.log(e.userInfo);
            console.log(e.userInfo.avatarUrl);
            console.log(e.userInfo.nickName);
            that.userinfo_img = e.userInfo.avatarUrl;
            that.userinfo_name = e.userInfo.nickName;
          },
          fail() {
            uni.showToast({
              icon: null,
              title: '您取消了登录授权'
            })
          }
        })
      },
      async get() {
        const [err, res] = await uni.login().catch(err => err);
        if (err || res.errMsg !== 'login:ok') {
          return uni.showToast({
            title: '登录失败!'
          })
        }
        console.log(res.code);
        this.query.code = res.code;
      }
    }

  }
</script>

<style lang="scss">
  page {
    background-color: #f6f6f6;
    margin: 0rpx 20rpx;
  }

  .userinfo {
    width: 94%;
    background-color: #ffffff;
  }


  .tableinformation {
    border-bottom: 20rpx solid #f6f6f6;
    width: 100%;
    height: 200px;
    display: flex;
    // background-image: url(@/stsatic/index_icons/bg-ac.jpg);
    justify-content: center;
    align-items: center;

    image {
      flex: 1;
      height: 150px;
      border-radius: 50%;
      background-color: aliceblue;
    }

    .tableinformation_name {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      p {
        flex: 1;
        font-size: 20px;
      }
    }
  }

  .tableinformation_img {
    flex: 0.15;
  }



  .el-button {
    margin-top: 20rpx;
    flex: 1;
    width: 48%;
    margin-bottom: 20rpx;
  }

  .buttomanniu {

    display: flex;
    width: 94%;
    // height: 100rpx;
    flex-wrap: wrap;
    padding: 20rpx;

    .el-button {
      // padding: 20rpx;
      margin-top: 30rpx;
      background-color: #ffffff;
      flex: 1;
      border: #e7e7e7;
      font-weight: bold;
      height: 150rpx;
      line-height: 150rpx;
      width: 48%;
    }

    uni-button:after {
      content: " ";
      width: 200%;
      height: 200%;
      position: absolute;
      top: 0;
      left: 0;
      border: 0px solid rgba(0, 0, 0, .2);
      -webkit-transform: scale(.5);
      transform: scale(.5);
      -webkit-transform-origin: 0 0;
      transform-origin: 0 0;
      box-sizing: border-box;
      border-radius: 10px;
    }

    .el-buttonkefu {
      background-image: url("@/static/us/kf.png");
      background-size: 100% 100%;
    }

    .el-buttonzf {
      background-image: url("@/static/us/fx.png");
      background-size: 100% 100%;
    }

    .el-buttonfk {
      background-image: url("@/static/us/fk.png");
      background-size: 100% 100%;
    }
  }

  .title {
    // margin-top: 30rpx;
    // width: 100%;
    // // margin-left: 150rpx;
    // padding-left: 8%;
    // font-weight: bold;
    // font-size: 40rpx;
    font-size: 40rpx;
    font-weight: bold;
    // margin: 0 auto;
  }

  .titlep {
    padding: 20rpx;
    font-size: 30rpx;
  }


  .aboutColor {
    // border: 2px solid #fd8204;
    // margin: 15px;
    border-radius: 15px;

    h1 {
      font-size: 40rpx;
      font-weight: bold;
    }

    p {
      // text-indent: 2em;
      margin: 10rpx;
    }
  }
</style>
