<template>
  <div class="container" style="position:relative">
    <div class="swiper-zone">
      <swiper  :indicator-dots="indicatorDots"
        :autoplay="autoplay" :interval="interval" :duration="duration">
        <block v-for="(item,index) in imgUrls" :key="index">
          <swiper-item >
            <image :src="item" class="slide-image" height="150"  width="355" style="width:100%;"/>
          </swiper-item>
        </block>
      </swiper>
    </div>
    <div class="icon-zone">
      <div class="icon-item">
        <ul >
          <li>
            <img src="../../../static/imgs/index.png" alt="" style="width:60px;height:60px;">
          </li>
          <li>
            商品分类
          </li>
        </ul>
      </div>
      <div class="icon-item">
        <ul >
          <li>
            <img src="../../../static/imgs/index.png" alt="" style="width:60px;height:60px;">
          </li>
          <li>
            商品分类
          </li>
        </ul>
      </div>
      <div class="icon-item">
        <ul >
          <li>
            <img src="../../../static/imgs/index.png" alt="" style="width:60px;height:60px;">
          </li>
          <li>
            商品分类
          </li>
        </ul>
      </div>
      <div class="icon-item">
        <ul >
          <li>
            <img src="../../../static/imgs/index.png" alt="" style="width:60px;height:60px;">
          </li>
          <li>
            商品分类
          </li>
        </ul>
      </div>
    </div>
    <div class="product-zone">
      <div class="product-item" @click="goToDetails">
        <ul>
          <li><img src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" alt="" style="width:100%;height:200px;"></li>
          <li>标题士大夫撒</li>
          <li>简介发防守打法</li>
          <li>价格</li>
          <li>预约</li>
        </ul>
      </div>
      <div class="product-item">
        <ul>
          <li><img src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" alt="" style="width:100%;height:200px;"></li>
          <li>标题士大夫撒</li>
          <li>简介发防守打法</li>
          <li>价格</li>
          <li>预约</li>
        </ul>
      </div>
      <div class="product-item">
        <ul>
          <li><img src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" alt="" style="width:100%;height:200px;"></li>
          <li>标题士大夫撒</li>
          <li>简介发防守打法</li>
          <li>价格</li>
          <li>预约</li>
        </ul>
      </div>
      <div class="product-item">
        <ul>
          <li><img src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" alt="" style="width:100%;height:200px;"></li>
          <li>标题士大夫撒</li>
          <li>简介发防守打法</li>
          <li>价格</li>
          <li>预约</li>
        </ul>
      </div>
    </div>
    <div class="foot-zone">
      <foot-bar></foot-bar>
    </div>
  </div>
</template>

<script>
import FootBar from '@/components/footBar'

export default {
  data () {
    return {
    imgUrls: [
      'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
      'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
      'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg'
    ],
    indicatorDots: true,
    autoplay: true,
    interval: 5000,
    duration: 1000
    }
  },

  components: {
    FootBar
  },
  methods: {
    wxSetTabBarItem() {
      wx.setTabBarItem(
        {
          index: 0,
          text: '首页',
          iconPath: '../../../static/imgs/index.png',
          selectedIconPath: '../../../static/imgs/index.png'
        },
        {
          index: 1,
          text: '分类',
          iconPath: '../../../static/imgs/index.png',
          selectedIconPath: '../../../static/imgs/index.png'
        },
        {
          index: 2,
          text: '预约',
          iconPath: '../../../static/imgs/index.png',
          selectedIconPath: '../../../static/imgs/index.png'
        },
        {
          index: 3,
          text: '我的',
          iconPath: '../../../static/imgs/index.png',
          selectedIconPath: '../../../static/imgs/index.png'
        }
      )
    },
    setPageTitle () {
      wx.setNavigationBarTitle({
        title: '小时光'
      })
    },
    setNavBarBgColor () {
      wx.setNavigationBarColor({
        frontColor: '#ffffff',
        backgroundColor: '#000000',
        animation: {
            duration: 400,
            timingFunc: 'easeIn'
        }
      })
    },
    showToast () {
      wx.showToast({
        title: '成功',
        icon: 'success',
        duration: 2000
      })
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              this.userInfo = res.userInfo
            }
          })
        }
      })
    },
    goToDetails () {
      console.log('挑战')
      wx.navigateTo({
        url: '../productDetails/main?id=1'
      })
    },
    clickHandle (msg, ev) {
      console.log('clickHandle:', msg, ev)
    }
  },
  created () {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo()
    this.wxSetTabBarItem()
    this.setPageTitle()
    this.setNavBarBgColor()
  },
  mounted () {
    // 调用应用实例的方法获取全局数据
    this.showToast()
    this.wxSetTabBarItem()
  }
}
</script>

<style scoped>
::-webkit-scrollbar {
  display: none;
  width: 0;
  height: 0;
  background-color: transparent;
}
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
.swiper-zone{
  width: 100%;
}
.container{
  padding-top: 0;
}
.icon-zone{
  display:flex;
  justify-content: space-around;
  width: 100%;
  margin: 10px 0;
}
.icon-item{
  width: 33%;
  text-align:center;
  font-size: 14px;
}
.product-zone{
  width: 100%;
  display:flex;
  justify-content: space-around;
  flex-wrap: wrap;
  font-size:14px;
}
.product-item{
  width:45%;
  border: 1px solid #ddd;
  margin-bottom:5px;
}
</style>
