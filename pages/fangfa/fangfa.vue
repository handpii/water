<template>
  <view class="content">

    <view class="title">
      <image src="../../static/ff/ff1.png"></image>生活污水治理方法
    </view>
    <view class="contenDetail">


      <uni-section title="1.农村生活污水治理方法" type="line" linecolor="#01b0fe">
        <p>工艺流程：生活污水→化粪池→厌氧池→人工湿地（种植根系发达、喜湿、吸收能力强的美人蕉、水葱、菖蒲等植物）经“过滤”后排放的方法进行处理，主要适用于农村分散生活污水处理，建成后运行费用基本为零，使用寿命在10年以上。
        </p>
        <image src="../../static/ff/ff2.png" mode=""></image>

      </uni-section>


      <uni-section title="2.城市生活污水治理方法" type="line" linecolor="#01b0fe">
        <p>
          将城市生活污水输送到城市周围的农村，利用农村广阔的土地来净化城市生活污水。将是一劳永逸与一举多得的好方法。以日供应生活用自来水100W立方的大中型城市为例：普通的污水处理设施造价1000元/立方。
        </p>
        <image src="../../static/ff/ff3.png" mode=""></image>

      </uni-section>

      <uni-section title="3.生活污水处理新技术：分散式处理" type="line" linecolor="#01b0fe">
        <p>
          生活污水分散式生物集成处理系统是针对生活污水的一种新型、经济环保的处理系统。该系统具备设备投资少、运行成本低、安装简便等优势，利用生物强化技术对污染物进行高效降解，可实现对生活污水就地、就近处理，并达到水资源循环再生利用的目的。该系统作为传统污水处理厂的污水处理的有效补充，逐步在城镇居住社区、宾馆酒店、旅游景区、新农村社区等领域得到广泛应用。
        </p>

        <p>分散式污水处理技术具有设备占地面积小、无须铺设管网、设备集成度高等特点，因此基础设施费用及土建费用在整体投资中占比较小，仅30%左右，而约有70%的投资主要用于对污水处理设备的采购和安装。
        </p>
        <image src="../../static/ff/ff5.png" mode=""></image>
      </uni-section>
    </view>


    <view class="title">
      <image src="../../static/ff/ff1.png"></image>生产废水治理方法
    </view>
    <view class="contenDetail">

      <uni-section title="工业污水的治理方法" type="line" linecolor="#01b0fe">
        <p>
          一种处理工业污水的方法，属于污水处理技术领域。其是将污水引往集水池，对集水池末尾一格调节pH，用一级溶气水泵提升到一级压力溶气罐，同时吸入空气和聚凝脱色剂，将在一级压力溶气罐内的一级饱和溶气水骤然释放到一级气浮池形成一级处理水；
        </p>

        <p>一级处理水溢入缓冲池，再在控制pH用二级溶气水泵将一级处理水提升至二级压力溶气罐内，同时吸入空气和聚凝脱色剂，将二级压力溶气罐内的二级饱和溶气水骤然释放到二级气浮池形成二级处理水并自溢至沉淀池沉淀后排放；
        </p>
        <image src="../../static/ff/ff4.png" mode=""></image>
      </uni-section>




      <view class="Textsp">*图片来源于网络如有侵权请私信删除</view>
    </view>
    <footerMsg />
  </view>
</template>

<script>
  export default {
    data() {
      return {

      }
    },
    methods: {

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

  .title {
    font-size: 50rpx;
    vertical-align: bottom;

    image {
      font-size: 0;
      height: 55rpx;
      vertical-align: bottom;
      width: 55rpx;
    }

  }

  .contenDetail {
    width: 100%;

    p {
      text-indent: 2em;
      padding: 0px 20rpx;
    }

    image {
      width: 100%;
      border-top: 15px solid #ffffff;
    }
  }

  .Textsp {
    font-size: 20rpx;
    color: #ccc;
  }
</style>
