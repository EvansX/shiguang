<template>
  <div class="productDetails-page">
    <div class="swiper-zone">
      <swiper  :indicator-dots="indicatorDots"
        :autoplay="autoplay" :interval="interval" :duration="duration" >
        <block v-for="(item,index) in imgUrls" :key="index">
          <swiper-item >
            <image :src="item" class="slide-image" height="240"  width="355" style="width:100%;"/>
          </swiper-item>
        </block>
      </swiper>
    </div>
   <div class="product-info">
     <div>
       <ul>
         <li>四重奏蛋糕</li>
         <li>“芒果茫茫+榴莲香雪+提拉米苏+黑森林”一次让你品尝四种不同口味！</li>
         <li ><span class="price">¥188</span></li>
       </ul>
     </div>
     <div class="tips">
       <p>雪顶榴心和榴莲千层为下午茶，只配刀叉和餐具，下单需谨慎</p>
     </div>
     <p>规格：</p>
     <div class="product-spec">
      <div class="spec-item">12颗</div>
      <div class="spec-item">24颗</div>
      <div class="spec-item">36颗</div>
     </div>
     <div class="details-intro">
       <div :class="toggleClass1" @click="toggleTab">图文详情</div>
       <div :class="toggleClass2" @click="toggleTab">产品参数</div>
       <div v-if="productPicShow" >
         <img src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" alt="" style="width:100%;">
         <img src="http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg" alt="" style="width:100%;">
         <img src="http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg" alt="" style="width:100%;">
         
       </div>
       <div v-if="!productPicShow" >
         <div>产品参数</div>
       </div>
     </div>
   </div>
   
     <div class="book-btn">立即预订</div>
  
  </div>
</template>

<script>

export default {
  components: {
  },

  data () {
    return {
      imgUrls: [
      'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
      'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
      'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg'
      ],
      indicatorDots: true,
      autoplay: false,
      interval: 5000,
      duration: 1000,
      toggleClass1: 'details-tab active',
      toggleClass2: 'details-tab',
      toggleClassActive: 'details-tab active',
      toggleClass: 'details-tab',
      productPicShow: true
    }
  },
  methods: {
    showModal () {
      console.log(1)
      wx.showModal({
        title: '提示',
        content: '这是一个模态弹窗',
        success: function(res) {
          if (res.confirm) {
            console.log('用户点击确定')
          } else if (res.cancel) {
            console.log('用户点击取消')
          }
        }
      })
    },
    toggleTab () {
      console.log("dsafa")
      this.productPicShow = !this.productPicShow
      if(this.productPicShow === false) {
        this.toggleClass1 = this.toggleClass
        this.toggleClass2 = this.toggleClassActive
      } else {
        this.toggleClass1 = this.toggleClassActive
        this.toggleClass2 = this.toggleClass
      }
    }
  },
  created () {
  }
}
</script>

<style>
::-webkit-scrollbar {
  display: none;
  width: 0;
  height: 0;
  background-color: transparent;
}
.productDetails-page{
  /* background:#CE1126; */
  /* position: relative; */
  padding-top:0;
  height: 100%;
}
.swiper-zone{
  height:240px;
}
._swiper{
  height:240px;
}
.product-info{
  padding:5px;
  height: 70px;
  font-size:14px;
  background: #fff;
  margin-bottom:5px;
  border: 1px solid #CE1126;
}
.price{
  color:#CE1126;
}
.tips{
  height:40px;
  margin: 5px 0;
  padding:5px;
  font-size:14px;
  background:#fff;
  border: 1px solid #CE1126;
}
.product-spec{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.spec-item{
  width:45%;
  border:1px solid #CE1126;
  margin-bottom:5px;
  text-align: center;
}
.details-tab{
  float:left;
  width: 50%;
  text-align: center;
  margin-top: 10px;
}
.details-intro .active{
  border-bottom: 1px solid #CE1126;
}
.book-btn{
  background:#CE1126;
  height:40px;
  width:100%;
  position: fixed;
  left:0;
  bottom:0;
  color:#fff;
  text-align: center;
  letter-spacing: 4px;
  line-height: 40px;
}
</style>
