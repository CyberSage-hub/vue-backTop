<template>
  <div>
      <!--回到顶部S-->
      <img id="backtop" v-show="show" v-on:touchstart="backTop" src="./h5_home_tanchu_fanhui.png" width="100%"/>
  </div>
</template>

<script>
var Vue = require('vue');
var VueRouter = require('vue-router');
Vue.use(VueRouter);
export default {
  data () {
    return {
        speed:0.5,
        show:false
    }
  },
  mounted:function(){
        let element = document.getElementsByClassName('home-content')[0];
        element.addEventListener("scroll", this.showBack);
  },
  methods:{
      showBack:function(e){
        if(e.target.scrollTop>window.screen.height){
            this.show = true;
        }else{
            this.show = false;
        }
      },
      backTop: function () {
        // 滚动到顶部
        let vm = this;
        //home-content为需要被滚动到顶部的元素
        //let element = document.body；
        let element = document.getElementsByClassName('home-content')[0];
        let top = element.scrollTop;
        let timer = setInterval(function () {
          top -= Math.abs(top * vm.speed);
          if (top <= 1) {
            top = 0;
            clearInterval(timer);
          }
          element.scrollTop = top;
        },20);
      }
  }
}
</script>

<style scoped>
#backtop{
    width: 1.12rem;
    height: 1.12rem;
    position: fixed;
    z-index: 999;
    bottom: 2.18666667rem;
    right: 0.53333333rem;
}
</style>
