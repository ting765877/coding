<template>
    <div class="playlist">
        <div class="playlist-top">
            <div class="left">
              <svg class="icon" aria-hidden="true">
                <use xlink:href="#icon-bofang"></use>
              </svg> 
              <div class="text">
                  <div class="title">
                      播放全部
                  </div>
                  <div class="num">(共{{playlist.tracks.length}}首)</div>
              </div>
            </div>
            <div class="btn">
                + 收藏（{{changeValue(playlist.subscribedCount)}}）
            </div>
        </div>
          <div class="list">
              <div class="playItem" v-for="(item,i) in playlist.tracks" :key="i">
                  <div class="left">
                   <div class="index">{{i+1}}</div>
                   <div class="content">
                       <div class="title">{{item.name}}</div>
                       <div class="author">
                           <span class="tag" v-for="(tag,index) in playlist.tags" :key="index">{{tag}}
                           </span>
                           <span>{{item.al.name}}</span></div>
                   </div>
                  </div>
                  <div class="right">
                   <svg class="icon" aria-hidden="true" @click="setPlayIndex(i)">
                    <use xlink:href="#icon-bofang1"></use>
                    </svg> 
                 <svg class="icon" aria-hidden="true">
                   <use xlink:href="#icon-sandian"></use>
                 </svg> 
                  </div>
              </div>
            </div>  
    </div>
</template>

<script>
import {  mapMutations} from 'vuex'
export default {
    props: ['playlist'],
    methods: {
        changeValue: function (num) {
            let res = 0
            if (num >= 100000000) {
                res = num / 100000000
                res = res.toFixed(2) + '亿'

            } else if (num > 10000) {
                res = num / 10000
                res = res.toFixed(2) + '万'
            }
            return res
        },
        ...mapMutations(['setPlayIndex'])
    },
}
</script>

<style lang="less" scoped>
.playlist{
    width: 7.5rem;
    padding: 0 0.4rem;
     background:linear-gradient(55deg,#CCFFFF,#FFCCCC);
     border-top-left-radius: 1rem;
     border-top-right-radius: 1rem;
     margin-top:0.4rem;
  
     .playlist-top{
    display: flex;
    justify-content: space-between;
    height:1.2rem;
    align-items: center;
    .left{
        display: flex;
        align-items: center;
      
        .icon{
            width: 0.5rem;
            height: 0.5rem;

        }
        .title{
            font-size: 0.35rem;
            font-weight: 800;
            margin-top: 00.01rem;
        }
        .num{
            font-size: 00.30rem;
            color:white;
            margin-top: 00.07rem;
        }
        .text{
            display: flex;
            justify-content: center;
            margin-left: 0.2rem;
           
        }
    }
    .btn{
        font-size: 00.30rem;
        color: white;
        background-color: pink;
        height: 0.8rem;
        line-height: 00.30rem;
        display: flex;
        padding: 00.25rem;
        border-radius: 50px;

    }
  }
           .list{
               .playItem{
                 display: flex;
                 justify-content: space-between ;
                 align-items: center;
                 height: 1.2rem;

                 .left{
                     display: flex;
                     align-items: center;
                     color: #666;
                     .index{
                         width: 0.2rem;
                         
                     }
                     .content{
                      margin-left: 00.4rem;
                     }
                     .title{
                         font-size: 0.33rem;
                         font-weight: 800;
                         color: black;
                         
                     }
                     .tag{
                         font-size: 00.17rem;
                         color: orangered;
                         border: 1px solid orange ;
                         border-radius: 00.1rem;
                         margin: 0.02rem;//华语流行
                     }
                     .author{
                          color: #666;
                    display: flex;
                    overflow: hidden;
                    height: 0.35rem;

                    .name {
                        width: 3rem;
                    }
                     }
                 }
                 .right{
                 .icon{
                      margin:0 0.01rem; 
                      width: 0.5rem;
                      height: 00.5rem;
                 }}
     }
 }
}
</style>