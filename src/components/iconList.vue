<template>
     <div class="iconList">
         <div class="iconItem">
             <svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-meirituijian"></use>
</svg> 
        <span>每日推荐 </span>

         </div>
         <div class="iconItem">
            <svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-sirenFM1"></use>
</svg> 
        <span>私人FM </span>
        </div>
         <div class="iconItem">
            <svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-faxian_gedan"></use>
</svg> 
        <span>歌单 </span>
        
         </div>
         <div class="iconItem">
           <svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-paihangbang1"></use>
</svg> 
        <span>排行榜 </span>
        
         </div>
     </div>
</template>

 
 <style lang='less' scoped>
 .iconList{
     width: 7.5rem;
     display:flex;
     justify-content: space-between;
     padding: 0.4rem;
     .iconItem{
         display: flex;
         flex-direction:column;
         align-items: center;
         .icon{
         width: 1rem;
         height:1rem;
     }
     }
     
 }
 </style>