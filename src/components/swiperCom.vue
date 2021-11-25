<template>
    <div class="swiper-container">
    <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="(item,i) in imgs" :key="i"> <img :src="item.pic"></div>

    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>
    
    
</div>
</template>
<script>

import 'swiper/css/swiper.css'
import Swiper from 'swiper';  
import axios from 'axios';
import {getBanner} from '@/api/index'
export default {
    data:function(){
      return{imgs:[
            { pic:require('../pic/swiper1.jpg'),},
            {pic:require('../pic/swiper2.jpg'),},
           {pic: require('../pic/swiper3.jpg'),},
              {pic:require('../pic/swiper4.jpg'),}
        ]}
    },
    async mounted(){
     
        let res = await getBanner(2)
        this.imgs = res.data.banners
        setTimeout(()=>{
            var mySwiper = new Swiper('#swiperIndex', {
                    loop: true, // 循环模式选项
                    // 如果需要分页器
                    pagination: {
                    el: '.swiper-pagination',
                    clickable:true,
                },
            });

        },10)
        
        
   }
}
</script>
<style >
.swiper-container{
  width:7.1rem;
  height:3.2rem;
 border-radius: 1rem;
}
.swiper-slide img{
    width: 100% ;
}
            img{
                width: 1.5rem;
                height: auto;
                border-radius:0.1rem;
            }
            .name{
                height:0.5rem;
                width:100%;
                font-size: 0.24rem;
            }
            .count{
                position: absolute;
                right:0.2rem ;
                top: 0.1rem;
                font-size: 0.1rem;
                color: #ccc;
               width: 1rem;
               display: flex;
               align-items: center;
            }

            
</style>