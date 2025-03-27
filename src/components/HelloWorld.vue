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
