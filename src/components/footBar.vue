<template>
  <div class="foot-zone">
   <div class="foot-box">
       <div class="foot-item">
         <ul>
            <li><img src="../../static/imgs/index.png" alt="" class="foot-icon-img"></li>
            <li>我的</li>
         </ul>
       </div>
       <div class="foot-item">
         <ul>
            <li><img src="../../static/imgs/index.png" alt="" class="foot-icon-img"></li>
            <li>我的</li>
         </ul>
       </div>
       <div class="foot-item">
         <ul>
            <li><img src="../../static/imgs/index.png" alt="" class="foot-icon-img"></li>
            <li>我的</li>
         </ul>
       </div>
       <div class="foot-item" @click="goToUserCenter">
         <ul>
            <li><img src="../../static/imgs/index.png" alt="" class="foot-icon-img"></li>
            <li>我的</li>
         </ul>
       </div>
   </div>
  </div>
</template>

<script>
export default {
  methods: {
    goToUserCenter () {
      wx.navigateTo({
        url: '../usercenter/main?id=1'
      })
    }
  }
}
</script>

<style>
.foot-zone{
  width: 100%;
  position: fixed;
  left:0px;
  bottom:0px;
  background:#ddd;
}
.foot-box{
  width:100%;
  height:50px;
  display:flex;
  border-top: 1px solid #ddd;
  justify-content: space-around;
  font-size:12px;
  align-items: center;
}
.foot-item{
  text-align:center;
}
.foot-icon-img{
  width:20px;
  height: 20px;
}
</style>
