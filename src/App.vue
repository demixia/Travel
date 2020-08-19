<!--组建模版-->
<template>
  <div id="app">
    <!--缓存-->
    <keep-alive exclude="Detail">
      <!-- 显示的是当前路由地址所对应的内容 -->
      <router-view/>
    </keep-alive>
  </div>
</template>
