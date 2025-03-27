<script setup>
import { ref, computed, watch } from 'vue'

// 当前选中的菜单
const currentMenu = ref('patent')

// 当前查看的教程
const currentTutorial = ref(null)

// 菜单配置【方式1：icon使用Font Awesome。缺点，图标大小不太一致，不好对齐，美观度不高】
// const menus = [
//     { id: 'patent', name: '翻译', icon: 'fas fa-language' },    // OK：Font Awesome图标搜索：https://fontawesome.dashgame.com/
//     { id: 'image', name: '截图', icon: 'fas fa-image' },
//     { id: 'mindmap', name: '思维图', icon: 'fas fa-project-diagram' },
//     { id: 'ppt', name: 'PPT', icon: 'fas fa-file-powerpoint' },
//     { id: 'pdf', name: 'PDF', icon: 'fas fa-file-pdf' },
//     { id: 'excel', name: 'Excel', icon: 'fas fa-file-excel' },
//     { id: 'format', name: '格式转换', icon: 'fas fa-exchange-alt' },
//     { id: 'ai', name: '飞书AI', icon: 'fas fa-robot' },
//     { id: 'screen', name: '录屏', icon: 'fas fa-video' },
//     { id: 'search', name: 'AI搜索', icon: 'fas fa-search' },
// ]

// // 菜单配置【方式2：icon使用elementplus，OK，方:2.1，使用引入函数变量】
// // import { ElIcon } from 'element-plus';
// import { Calendar, Search } from '@element-plus/icons-vue'
// const menus = [
//     { id: 'patent', name: '翻译', icon: Search },
//     { id: 'image', name: '截图', icon: Calendar },
//     { id: 'mindmap', name: '思维图', icon: Calendar },
//     { id: 'ppt', name: 'PPT', icon: Calendar },
//     { id: 'pdf', name: 'PDF', icon: Calendar },
//     { id: 'excel', name: 'Excel', icon: Calendar },
//     { id: 'format', name: '格式转换', icon: Calendar },
//     { id: 'ai', name: '飞书AI', icon: Calendar },
//     { id: 'screen', name: '录屏', icon: Calendar },
//     { id: 'search', name: 'AI搜索', icon: Search },
// ]
// 菜单配置【icon使用elementplus，OK，方式2.2，使用字符串】
const menus = [
  { id: 'patent', name: '专利', icon: 'Operation' },
  { id: 'standard', name: '标准', icon: 'Crop' },
  { id: 'paper', name: '文献', icon: 'Share' },
  { id: 'sae', name: 'SAE', icon: 'Edit' },
  { id: 'wenku', name: '文库', icon: 'Document' },
  // { id: 'excel', name: 'Excel', icon: 'Notebook' },
  // { id: 'format', name: '格式转换', icon: 'RefreshRight' },  // Guide
  // { id: 'ai', name: '飞书AI', icon: 'ChatDotRound' },
  // { id: 'screen', name: '录屏', icon: 'VideoCamera' },
  // { id: 'search', name: 'AI搜索', icon: 'Search' },
]




// 工具列表数据
const allTools = [
  {
    id: 1,
    // name: 'ChatPPT',
    // logo: '/chatppt-logo.png',
    // logo: '/images/fdmai_avatar.png',
    // image: '/images/digital resource library/专利/logo-chatPPT.jpg',   // 注：使用相对路径vite工具时，图片位于public文件夹
    // description: 'AI生成PPT内容和格式，支持一键生成精美PPT',
    // rating: 5,
    // link: '#',
    // link: 'https://chat-ppt.com/',
    // categories: ['ppt', 'ai'],
    categories: ['patent'],

  },
  {
    id: 2,
    // name: 'Gamma',
    // image: '/images/AIEfficiencyTool/logo-Gamma.jpg',
    // description: '智能PPT生成工具，让演示文稿制作更简单',
    // rating: 3,
    // link: '#',
    // link: 'https://gamma.app/',
    // categories: ['ppt', 'ai'],
    categories: ['standard'],
  },
  {
    id: 3,
    // name: 'Gamma',
    // image: '/images/AIEfficiencyTool/logo-Gamma.jpg',
    // description: '智能PPT生成工具，让演示文稿制作更简单',
    // rating: 3,
    // link: '#',
    // link: 'https://gamma.app/',
    // categories: ['ppt', 'ai'],
    categories: ['paper'],
  },
  {
    id: 4,
    // name: 'Gamma',
    // image: '/images/AIEfficiencyTool/logo-Gamma.jpg',
    // description: '智能PPT生成工具，让演示文稿制作更简单',
    // rating: 3,
    // link: '#',
    // link: 'https://gamma.app/',
    // categories: ['ppt', 'ai'],
    categories: ['sae'],
  },
  {
    id: 5,
    // name: 'Gamma',
    // image: '/images/AIEfficiencyTool/logo-Gamma.jpg',
    // description: '智能PPT生成工具，让演示文稿制作更简单',
    // rating: 3,
    // link: '#',
    // link: 'https://gamma.app/',
    // categories: ['ppt', 'ai'],
    categories: ['wenku'],
  },


]

// 监听菜单变化
// watch(currentMenu, (newMenu) => {
//     // 无论当前是否在查看教程，都返回到工具列表
//     currentTutorial.value = null
// })

// 计算属性：根据当前菜单过滤工具
const filteredTools = computed(() => {
  return allTools.filter(tool => tool.categories.includes(currentMenu.value))
})
// const filteredTools = computed(function() {
//     return allTools.filter(function(tool123) {    // tool123 是 filter 方法的回调函数的参数。filter 方法会自动将数组中的每一个元素传递给回调函数，因此 tool123 代表 allTools 数组中的每一个工具对象。
//         return tool123.categories.includes(currentMenu.value);
//     });
// });

// 计算属性：获取当前菜单对应的标签
// const currentTags = computed(() => {
//   return tagsByMenu[currentMenu.value] || []
// })
// const currentTags = () => {
//   console.log('currentTags = tagsByMenu[currentMenu.value]:', tagsByMenu[currentMenu.value])
//   return tagsByMenu[currentMenu.value] || []
// }

// 显示教程的方法
const showTutorial = (tool) => {
  currentTutorial.value = tool
  if (!tool.categories.includes(currentMenu.value)) {
    currentMenu.value = tool.categories[0]
  }
}

// 返回列表的方法
const backToList = () => {
  currentTutorial.value = null
}

// 处理菜单点击
const handleMenuClick = (menuId) => {
  // 更新当前菜单
  currentMenu.value = menuId
  // 清除当前教程显示
  currentTutorial.value = null
}



// 获取工具logo的路径处理
// 定义获取图像 URL 的方法
const getImageUrl = (path) => {
  return new URL(path, import.meta.url).href;  // import.meta.url 是一个特殊的元属性，它包含当前模块的 URL。通过将相对路径 path 与 import.meta.url 结合，new URL 构造函数能够生成一个绝对 URL。最后，函数返回生成的 URL 的 href 属性，这个属性包含了图像的完整 URL 字符串。
};




</script>

<template>
  <div class="ai-tools">
    <!-- 标题部分 -->
    <h1 class="title">数字资源库</h1>

    <!-- 导航链接 -->
    <div class="nav-link">
      <a href="https://navi.fdmgpt.top" class="link" target="_blank">
        友情链接: FDM AI导航站
      </a>
    </div>

    <!-- 主体内容容器 -->
    <div class="container">
      <!-- 左侧菜单 -->
      <div class="sidebar">
        <div v-for="menu in menus" :key="menu.id" :class="['menu-item', { active: currentMenu === menu.id }]"
          @click="handleMenuClick(menu.id)">

          <el-icon class="mr-2">
            <component :is="menu.icon" />
          </el-icon>

          <span class="menu-text">{{ menu.name }}</span>
        </div>
      </div>

      <!-- 主内容区 -->
      <div class="main-content">

        <!-- 工具卡片列表 -->
        <div class="tools-grid">
          <div v-for="tool in filteredTools" :key="tool.id" class="tool-card">
            <!-- {{ tool.categories }}
            {{ tool.categories[0] }} -->



            <!-- 设置专利 -->
            <div v-if="tool.categories[0] === 'patent'">


              <!-- 设置专利方式1 -->
              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px;">

                
                <!-- <p style="font-weight: bold;">1.国家知识产权局官方专利检索/下载服务</p> -->
                <div style="display: flex; justify-content: left; align-items: center;">
                  <p style="font-weight: 100;">1.国家知识产权局官方专利检索/下载服务</p>
                  <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                    【官方权威】【免费】【中外多国专利】
                  </span>
                </div>
                <!-- <p style="font-weight: 100;">1.国家知识产权局官方专利检索/下载服务</p>
                <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                  【官方权威】【免费】【中外多国专利】
                </span> -->

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://pss-system.cponline.cnipa.gov.cn/Initpage" target="_blank">国家知识产权局-专利高级检索服务 </a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【官方权威】【免费】【中外多国专利】
                      </span>
                    </li>
                    <li>
                      <a href="https://pss-system.cponline.cnipa.gov.cn/Initpage" target="_blank">国家知识产权局 </a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【国家知识产权局专利服务中转链接】
                      </span>
                    </li>
                  </ul>


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <!-- <span style="flex: 1; height: 1px; background-color: #ccc;  border: 1px dashed;"></span> -->
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">官网页面</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <!-- {{ tool.image }} -->
                  <img src="/images/digital resource library/专利/国家知识产权局.jpg" :alt="国家知识产权局官网" class="step-image">
                  <img src="/images/digital resource library/专利/专利检索及分析系统.jpg" :alt="专利检索及分析系统" class="step-image">

                </div>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      注册教程：使用身份证号和手机号码，可按照提示快速注册。
                    </li>
                    <li>
                      使用示例：
                    </li>
                  </ul>


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step1</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/专利/国家知识产权局-专利检索服务-使用示例1.jpg" :alt="国家知识产权局 - 专利检索服务 - 使用示例1"
                    class="step-image">


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step2</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/专利/国家知识产权局-专利检索服务-使用示例2.jpg" :alt="国家知识产权局 - 专利检索服务 - 使用示例2"
                    class="step-image">


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step3</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/专利/国家知识产权局-专利检索服务-使用示例3.jpg" :alt="国家知识产权局 - 专利检索服务 - 使用示例3"
                    class="step-image">

                </div>
              </div>




              <!-- 设置专利方式2 -->
              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px; margin-top:100px;">
                <p style="font-weight: 100;">2.其它免费专利下载渠道</p>
                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://www.drugfuture.com/cnpat/cn_patent.asp" target="_blank">drugfuture</a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【中外专利免费下载】【无需注册】【推荐】
                      </span>
                    </li>
                    <li>
                      <a href="https://www.patentstar.com.cn/" target="_blank">专利之星 </a>
                    </li>
                  </ul>

                </div>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      drugfuture【推荐】：网页下方可选择欧洲专利、美国专利、Patent9专利搜索（中文专利）。搜索相关专利信息即可访问。
                    </li>
                    <li>
                      专利之星：您可阅读<a href="https://kdocs.cn/l/clh03gxBnffX/" target="_blank">帮助文档</a><span>帮助文档</span>
                      。
                    </li>
                  </ul>
                </div>
              </div>
              
              



            </div>





            <!-- 设置标准 -->
            <div v-if="tool.categories[0] === 'standard'">


              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px;">

                
                <!-- 设置标准方式1 -->
                <div style="display: flex; justify-content: left; align-items: center;">
                  <!-- <p style="font-weight: bold;">1.国家知识产权局官方专利检索/下载服务</p> -->
                  <p style="font-weight: 100;">1.国家标准全文公开系统标准检索/查看服务</p>
                  <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                    【官方权威】【免费】
                  </span>
                </div>
                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://openstd.samr.gov.cn/bzgk/gb/" target="_blank">国家标准全文公开系统</a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【免费标准检索、查看】【推荐】
                      </span>
                    </li>
                  </ul>


                </div>





                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">



                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step1</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/标准/国家标准全文公开系统.jpg" :alt="国家标准全文公开系统" class="step-image">


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step2</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/标准/国家标准全文公开系统1.jpg" :alt="国家标准全文公开系统1" class="step-image">


                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step3</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/标准/国家标准全文公开系统2.jpg" :alt="国家标准全文公开系统2" class="step-image">

                  <div style="display: flex; align-items: center; margin-top: 20px;">
                    <span style="flex: 1; height: 1px; background-color: #ccc; "></span>
                    <span style="margin: 0 10px; color: #666;">step4</span>
                    <span style="flex: 1; height: 1px; background-color: #ccc;"></span>
                  </div>

                  <img src="/images/digital resource library/标准/国家标准全文公开系统3.jpg" :alt="国家标准全文公开系统3" class="step-image">

                </div>
              </div>





              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px; margin-top:100px;">

                
                <!-- 设置标准方式2 -->
                <p style="font-weight: 100;">2.其它免费标准查看/下载渠道</p>


                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="http://www.bzfxw.com/" target="_blank">学兔兔</a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【微信扫码登录】【普通用户每天2篇】
                      </span>
                    </li>
                    <li>
                      <a href="https://www.bzxz.net/" target="_blank">标准下载网 </a>
                    </li>
                    <li>
                      <a href="https://www.doc88.com/" target="_blank">道客巴巴 </a>
                    </li>
                    <li>
                      <a href="https://www.docin.com/" target="_blank">豆丁网 </a>
                    </li>
                    <li>
                      <a href="https://max.book118.com/" target="_blank">原创力文档（book118） </a>
                    </li>

                  </ul>

                </div>





                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      drugfuture【推荐】：网页下方可选择欧洲专利、美国专利、Patent9专利搜索（中文专利）。搜索相关专利信息即可访问。
                    </li>
                    <li>
                      标准资源库，免费使用渠道见访问链接。您可阅读<a href="https://www.kdocs.cn/l/cjFPcOIwXBIq">帮助文档</a><span>帮助文档</span>
                      。
                    </li>
                  </ul>

                </div>

              </div>








            </div>






















            <!-- 设置文献 -->
            <div v-if="tool.categories[0] === 'paper'">

              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px;">

              
                <!-- 设置文献方式1 -->
                <!-- <p style="font-weight: bold;">1.国家知识产权局官方专利检索/下载服务</p> -->
                <p style="font-weight: 100;">1.常用中英文献检索/下载</p>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://my.s99s.top/" target="_blank">中国知网镜像 </a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【已购买公共账户】【账号&密码在使用教程中帮助文档】
                      </span>
                    </li>
                    <li>
                      <a href="https://www.ablesci.com/" target="_blank">中国知网镜像 </a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【优点：文献全面，其它地方无法获取的文献可在此处下载】
                      </span>
                    </li>
                    <li>
                      <a href="https://sci-hub.se/" target="_blank">SCI Hub </a>
                    </li>
                  </ul>


                </div>


                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      常用中文文献资源库，免费使用渠道见访问链接。您可阅读<a href="https://www.kdocs.cn/l/cuhg2xwj7z0U">帮助文档</a><span>帮助文档</span>
                      。
                    </li>
                  </ul>

                </div>
              </div>
            </div>



            <!-- 设置sae -->
            <div v-if="tool.categories[0] === 'sae'">


              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px;">
                <!-- <p style="font-weight: bold;">1.国家知识产权局官方专利检索/下载服务</p> -->
                <p style="font-weight: 100;">1.SAE论文检索/下载</p>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://saemobilus.sae.org/" target="_blank">SAE论文 </a>
                      <span style="background-color: #F8F9FB; color: #09AB3B; font-size: 12px;">
                        【官网查询DOI，配合科研通和SCIHub使用】
                      </span>
                    </li>
                  </ul>


                </div>


                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      SAE论文资源库，免费使用渠道见访问链接。您可阅读<a href="https://www.kdocs.cn/l/cseMTB8oH0K3">帮助文档</a><span>帮助文档</span>
                      。
                    </li>
                  </ul>

                </div>
              </div>
            </div>










            <!-- 设置文库 -->
            <div v-if="tool.categories[0] === 'wenku'">

              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px;">

              
                <!-- <p style="font-weight: bold;">1.国家知识产权局官方专利检索/下载服务</p> -->
                <p style="font-weight: 100;">1.驱动视界文档库</p>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="http://www.qdsj.net.cn/downloadlist/12-1.shtml/" target="_blank">驱动视界文档库 </a>
                    </li>
                  </ul>


                </div>


                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      驱动视界文档库，点击网页即可访问。
                    </li>
                  </ul>

                </div>

              </div>


              <div style="border: 1px solid #ccc; padding: 10px; border-radius: 5px; margin-top: 100px;">
                <p style="font-weight:100">2.文库资料免费下载/在线复制文本</p>

                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  访问链接
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>
                      <a href="https://www.tampermonkey.net/" target="_blank">tampermonkey浏览器扩展 </a>
                    </li>
                    <li>
                      <a href="https://greasyfork.org/zh-CN/" target="_blank">tampermonkey用户脚本下载 </a>
                    </li>
                  </ul>


                </div>


                <div
                  style="margin-top:10px; font-weight: bold; background-color: #E8F2FC; height: 50px; display: flex; align-items: center; padding-left: 20px; border-radius: 6px;">
                  使用教程
                </div>

                <div style="margin-top: 19px;">
                  <ul>
                    <li>                    
                      【浏览器扩展】文库资料免费下载/在线复制文本等多种功能的宝藏脚本，使用教程请阅读<a href="https://www.kdocs.cn/l/cgj5ABczWXNe">帮助文档</a>
                      。
                    </li>
                  </ul>

                </div>
              </div>












            </div>








          </div>
        </div>
      </div>
    </div>



  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
