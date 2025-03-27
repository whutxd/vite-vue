<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>

  <div class="ai-tools">
    <!-- 标题部分 -->
    <h1 class="title">FDM AI导航站</h1>
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="http://fdmai.top/" class="link" target="_blank">
        <h2>1.FDM AI平台</h2>
      </a>
    </div>

    
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="http://fdmgpt.top" class="link" target="_blank">
        <h2>2.FDM ChatGPT</h2>
      </a>
    </div>
    

    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="http://navi.fdmgpt.top" class="link" target="_blank">
        <h2>3.FDM ChatGPT（free）</h2>
      </a>
    </div>

    
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="https://navi.fdmgpt.top" class="link" target="_blank">
        <h2>4.FDM AI效率工具+数字资源库</h2>
      </a>
    </div>

    
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="http://oa.fdm.com.cn/wui/main.jsp?templateId=7" class="link" target="_blank">
        <h2>5.FDM OA平台</h2>
      </a>
    </div>


    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="https://fdm.com.cn/" class="link" target="_blank">
        <h2>6.FDM官网</h2>
      </a>
    </div>

 
  </div>











  
  <h1>{{ msg }}</h1>

  <p class="read-the-docs">Click on the Link and Have Fun！</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

h2 {
    display: inline-block; /* 使链接能够设置宽高 */
    text-decoration: none; /* 去掉下划线 */
    padding: 10px 20px; /* 添加内边距 */
    background-color: #007bff; /* 背景颜色 */
    color: white; /* 字体颜色 */
    border-radius: 15px; /* 圆角 */
    transition: transform 0.3s; /* 添加平滑过渡效果 */
}
  
h2:hover {
  transform: scale(1.1); /* 鼠标悬停时放大 */
}
</style>
