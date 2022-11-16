<template>
  <view class="width">
    <view v-for="(item,index) in lists" :key="index">
      <view v-if="item.id == idname">
        <view class="title"> {{item.title}}</view>
        <view class="script"> {{item.script}}</view>
        <image :src="item.imgsrc"></image>
        <view class="script"> {{item.script_}}</view>
        <image :src="item.imgsrc_"></image>
        <view class="Textsp">*图片来源于网络如有侵权请私信删除</view>
      </view>
    </view>
    <footerMsg />
  </view>
</template>

<script>
  export default {
    data() {
      return {
        idname: 0,
        lists: [{
          id: 1,
          title: "生产污水处理",
          script: "生产污水专指工矿企业生产中所排出的玷污较严重、须经处理后方可排放的工业废水。成分复杂，多半具有较大的危害性，各种生产污水的水质和水量相差很大。对一种生产污水，往往以其中含量较多或毒性较强的某一种成分来命名，如含酚、含油、酸碱、含氰、含砷、含铬、含汞。含镉、含铅等污水。",
          imgsrc: '/static/index/detail1.jpg',
          script_: "按生产污水中的污染物，可分为两类，(1)其污染物质能在环境或动植物体内蓄积，对人体健康产生长远不良影响，包括总汞、有机汞、总镉、六价铬、总铬、总砷、总铅、有机铅、总镍和多氯联苯等，这类生产污水一律要求在车间或处理设备的排出口达到规定的排放标准。(2)其他污染物，包括悬浮物、石油类、挥发酚、氰化物、氟、阴离子表面活性剂、磷酸盐、有机磷、甲醛、苯胺、硝基苯、苯系物、铜、锌、锰等。生产污水中还可能含有难分解的有机物多主要是有机氯化合物、多环有机化合物、有机氮化合物(芳香胺类)和有机重金属化合物等，其中有不少难分解有机物是致癌物。",
          imgsrc_: '/static/index/detail2.jpg'

        }, {
          id: 2,
          title: "生活污水处理",
          script: "生活污水是居民日常生活中排出的废水，主要来源于居住建筑和公共建筑，如住宅、机关、学校、医院、商店、公共场所及工业企业卫生间等。生活污水所含的污染物主要是有机物(如蛋白质、碳水化合物、脂肪、尿素、氨氮等) 和大量病原微生物(如寄生虫卵和肠道传染病毒等)。存在于生活污水中的有机物极不稳定，容易腐化而产生恶臭。细菌和病原体以生活污水中有机物为营养而大量繁殖，可导致传染病蔓延流行。因此，生活污水排放前必须进行处理。",
          imgsrc: '/static/index/detail3.jpg',
          script_: "主要来自城市生活污水、医院污水、垃圾及地面径流等方面。病原微生物的特点是：①数量大；②分布广；③存活时间较长；④繁殖速度快；⑤易产生抗性，很难消灭；⑥传统的二级生化污水处理及加氯消毒后，某些病原微生物、病毒仍能大量存活；此类污染物实际上通过多种途径进入人体，并在体内生存，引起人体疾病。",
          imgsrc_: '/static/index/detail4.jpg'
        }]

      };
    },
    onLoad(option) {
      this.idname = option.id
      // console.log(option.id)
    }
  }
</script>

<style lang="scss">
  page {
    background-color: #f6f6f6;
    margin: 0px 20rpx;
  }

  .width {
    width: 94%;
    background-color: #ffffff;
  }

  .title {
    border-radius: 15px;
    font-size: 30px;
    font-family: "FZChaoCuHei-M10S", "Microsoft YaHei";
    text-align: center;
    line-height: 70px;
    height: 70px;
    background-color: #ffffff;
  }

  .script {
    text-indent: 2em;
    padding: 20rpx;
    border-top: 20rpx solid #f5f5f5;
    font-family: "FZChaoCuHei-M10S", "Microsoft YaHei";
    background-color: #ffffff;
  }

  .photo {
    text-align: center;
    background-color: #ffffff;
  }

  image {
    width: 100%;
  }

  .Textsp {
    font-size: 20rpx;
    background-color: #fff;
    color: #ccc;
  }
</style>
