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
    <h1 class="title">FDM AI平台</h1>
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="http://fdmai.top/" class="link" target="_blank">
        FDM AI平台
      </a>
    </div>

    <!-- 标题部分 -->
    <h1 class="title">数字资源库</h1>
    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="https://navi.fdmgpt.top" class="link" target="_blank">
        友情链接: FDM AI导航站
      </a>
    </div>












    
  </div>











  
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
