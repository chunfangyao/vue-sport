<template>
  <view>
    <img mode="aspectFill" :src="src" class="header-img"></img>
    <view class="content">
      <view class="search-contain">
        <input class="uni-input" focus placeholder="项目类型，或者地点" placeholder-class="placeholder-class"/>
        <view class="address">上海</view>
        <img src="../../static/index/search-icon.png" mode="" class="search-icon"/>
        <img src="../../static/index/down.png" mode="" class="down-icon" />
      </view>
      <swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" interval="5000">
        <swiper-item class="swiper-item">
          <img src="https://pic.qulianying.com/fab32797-90ce-5c36-011d-36e34845bd10.jpg" mode="aspectFill"
                 class="swiper-img" />
        </swiper-item>
        <swiper-item class="swiper-item">
          <img src="https://pic.qulianying.com/fab32797-90ce-5c36-011d-36e34845bd10.jpg" class="swiper-img"
                 mode="aspectFill" />
        </swiper-item>
      </swiper>
      <scroll-view class="scroll-view" scroll-x="true" show-scrollbar="true" @scroll="bingScroll">
        <view id="demo1" class="scorll-view-item">
          <img src="https://pic.qulianying.com/f5ddc774-d9c0-abf6-50f7-54c256bd331d.png" mode="aspectFill" />
        </view>
        <view id="demo1" class="scorll-view-item">
          <img src="https://pic.qulianying.com/71eabeb9-6009-1039-bc4a-bf2ed8914a0c.png" mode="aspectFill" />
        </view>
        <view id="demo1" class="scorll-view-item">
          <img src="https://pic.qulianying.com/82ae81a2-8f09-2b38-1501-6527c779e927.png" mode="aspectFill" />
        </view>
        <view id="demo1" class="scorll-view-item">
          <img src="https://pic.qulianying.com/6066072c-c523-160a-1166-f0ed9814de63.png" mode="aspectFill" />
        </view>
        <view id="demo1" class="scorll-view-item">
          <img src="https://pic.qulianying.com/824c4e77-3279-ebcd-5f09-6159469f790c.png" mode="aspectFill"/>
        </view>
      </scroll-view>

      <view class="scroll-bar">
        <view class="scroll-bar__bg">
          <view class="scroll-bar__slide" :style="{width: width + 'rpx',left:scrollLeft + 'rpx'}"></view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
import navTop from '@/components/navTop.vue'

export default {

  components: {
    navTop
  },

  data() {
    return {
      navTop: {
        title: '趣练鹰',
        bgColor: '#ffaaaa'
      },
      src: '../../static/index/background.png',
      background: ['color1', 'color2', 'color3'],
      indicatorDots: true,
      autoplay: true,
      width: 40,
      left: '',
      scrollLeft: 0,
    }
  },

  onLoad() {

  },

  methods: {
    // bindScroll:function(e) {
    // 	console.log(e,'13213123')
    //  this.width = e.detail.scrollWidth;
    //  console.log(this.width)
    // let left = e.detail.scrollLeft;
    // let autoWidth = width - uni.getSystemInfoSync().windowWidth;
    // let scrollLeft = left / autoWidth; //移动的百分比
    // scrollLeft = scrollLeft * 100 * 0.39;
    // this.setData({
    // 	scrollLeft: scrollLeft
    // })
    // },
  }
}
</script>

<style lang="scss">
@import url("./index.scss");
</style>
