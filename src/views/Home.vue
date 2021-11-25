<template>
  <div class="home">
    <top-nav></top-nav>
    <swiper-com></swiper-com>
    <icon-list></icon-list>
    <music-list></music-list>
  </div>
</template>

<script>
import topNav from '@/components/topNav.vue'
import swiperCom from '@/components/swiperCom.vue'
// import style (>= Swiper 5.x)
import iconList from '@/components/iconList.vue'//引入图标组件
import musicList from '@/components/musicList.vue'
export default {
  name:'Home',
  components: {
    topNav,swiperCom,iconList,musicList
  },
data:function(){
    return {
     
    }
  },
  computed:{
    
  },
  

}

</script>
<style lang="less" scoped>
#d1{
  width:3.75rem;
  height: 3.75rem;
  background: greenyellow;
}

</style>