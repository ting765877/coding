<template>
 <div class="listViewTop" >
        <img class="bg" :src="playlist.coverImgUrl" >
        <div class="listViewTopNav">
            <div class="back" @click="$router.go(-1)">
                 <svg class="icon zuo" aria-hidden="true">
                 <use xlink:href="#icon-zuojiantou"></use>
                 </svg>
                 <div class="title">歌单</div>
            </div>
            <div class="right">
                <svg class="icon search" aria-hidden="true">
                 <use xlink:href="#icon-sousuo1"></use>
                 </svg>
                 <svg class="icon" aria-hidden="true">
                 <use xlink:href="#icon-sandian"></use>
                 </svg>
            </div>
        </div>

        <div class="content">
            <div class="contentLeft">
                <img :src="playlist.coverImgUrl" >
                    <div class="count"><svg class="icon" aria-hidden="true">
                           <use xlink:href="#icon-24gl-play"></use>
                            </svg> 
                            <span>{{changeValue(playlist.playCount)}}</span>
                            </div> 
            </div>
            <div class="contentRight">
            <h3>  {{playlist.name}}</h3>
            <div class="author">
               <img class="header" :src="playlist.creator.avatarUrl">
               <span>{{playlist.creator.nickname}}</span>
            </div>
            <div class="description">
                {{playlist.description}}
            </div>
            </div>
        </div>
        <div class="iconList">
            <div class="iconItem">
                <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-xiaoxi"></use>
                </svg> 
                <span>{{playlist.commentCount}}</span>
            </div>
            <div class="iconItem">
                <svg class="icon" aria-hidden="true">
                 <use xlink:href="#icon-weibiaoti-"></use>
                </svg> 
                <span>{{playlist.shareCount}}</span>
            </div>
            <div class="iconItem">
                <svg class="icon" aria-hidden="true">
               <use xlink:href="#icon-download"></use>
                </svg> 
                <span>下载</span>
            </div>
            <div class="iconItem">
                <svg class="icon" aria-hidden="true">
               <use xlink:href="#icon-duoxuan"></use>
                </svg> 
                <span>多选</span>
            </div>
        </div>
    </div>


</template>


<script>
export default{
    props:['playlist'],
    mounted() {
        console.log(this.props)
    },
     methods: {
        changeValue:function(num){
            let res=0
                  if(num>=100000000){    
                  res=num/100000000
               res=res.toFixed(2)+'亿'
               }else if(num>10000){
                     res=num/10000
                    res=res.toFixed(2)+'w'
                                 }
                          return res
                                   }
                            },
                  }
</script>


<style lang="less" scoped>
 .listViewTop{
     width: 7.5rem;
     padding: 0 0.4rem;

     .bg{
         position: fixed;
         left: 0;
         top: 0;
         width: 7.5rem;
         height: auto;
         z-index: -1 ; //透明
         filter:blur(7px);//模糊设置
     }
     .listViewTopNav{
          display: flex;
          justify-content: space-between;
          align-items: center;
          height: 1.2rem;
          font-size: 0.4rem;
          .icon{
              width: 0.5rem;
              height: 0.5rem;
              fill: rgb(240, 254, 255);
          }
          .zuo{
              width: 0.7rem;
              height: 0.7rem;
             
          }
          .title{
              margin-left: 0.4rem;
              margin-top: 00.07rem;
          }
          .search{
              margin-right: 0.5rem;
          }
     }
     .back,.right{
         display: flex;
         color: honeydew;
     }
     .content{
         display: flex ;
         justify-content: space-between ;
         padding: 0.5rem 0;
         .contentLeft{
             position: relative;
             img{
                 width: 3rem;
                 height: 3rem;
                 border-radius: 5rem;
             }
             
           .count{
                position: absolute;
                right:0.1rem ;
                top: 0.1rem;
                font-size: 0.1rem;
                color: #ccc;
               width: 1rem;
               display: flex;
               align-items: center;
               margin-right: 1rem;
            }
         }
         .contentRight{
             width: 3.5rem;
             h3{
                 color:white
             }
             .author{
             display: flex;
             align-items: center;
             margin: 00.2rem 0.1rem;
             img.header{
                 width: 0.6rem;
                 height: 0.6rem;
                 border-radius: 5rem;
                 margin-right: 00.24rem;
             }
             span{
                 color: #ccc;
             }
             }
             .description{
                 margin: 0.1rem 0;
                 font-size: 0.2rem;
                 color:white;
                 overflow: hidden;
                 text-overflow: ellipsis;
                 display: -webkit-box;
                 -webkit-line-clamp: 2;
                 -webkit-box-orient: vertical ;
             }
         }
     }
      .iconList{
          display: flex;
          justify-content: space-around;
          align-items: center;
           margin-left: 00.1rem ;
          .iconItem{
              display: flex;
              flex-direction: column;
              .icon{
                
                  width: 0.5rem;
                  height: 00.5rem;
                  fill: white;
              }
              span{
                  color: white;
              }
            
          }
      }
 }
</style>