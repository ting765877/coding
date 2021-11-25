<template>
    <div class="topNav">
    <div class="topLeft">
      <svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-24gl-playlistHeart2"></use>
</svg><!--字体图标写法-->
    </div>
    <div class="topCenter">
      <span class="navBtn" @click="$router.push('/me')">我的</span>
      <span class="navBtn active">发现</span>
      <span class="navBtn">云村</span>
      <span class="navBtn">视频</span>
    </div>
    <div class="topRight" @click="$router.push('/searchview')">
      <svg class="icon search" aria-hidden="true">
    <use xlink:href="#icon-sousuo"></use>
</svg>
    </div>
  </div>
</template>

<style lang="less" scoped>
.topNav{
    width:7.5rem;
    height:1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding:0 0.25rem;
    .icon{
        width: 0.5rem;
        height: 00.5rem;
    }
    .search{
        width: 0.45rem;
        height: 00.45rem;
    }
    .topCenter{
        width: 4.5rem;
        display: flex;
        justify-content: space-around;
        .active{
            font-weight: 900;
        }
    }
}
</style>