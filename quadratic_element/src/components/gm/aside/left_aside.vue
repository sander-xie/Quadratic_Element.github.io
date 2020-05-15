<template>
  <div>
    <el-menu default-active="1" class="el-menu-vertical-demo" :collapse="isCollapse">
      <!-- 暂时不开放展开功能 @click="isCollapse=!isCollapse" -->
        <el-menu-item index="1" >
          <i class="el-icon-s-unfold" v-if="isCollapse"></i>
          <i class="el-icon-s-fold" v-if="!isCollapse"></i>
          <span slot="title">阿勒勒，这都被你发现啦？</span>
        </el-menu-item>
        <!-- 一级-前端开发-START 5 -->
        <el-submenu index="5">
          <template slot="title">
          <i class="el-icon-s-platform"></i>
          <span slot="title">{{$t('m.fed.name')}}</span>
          </template>
          <!-- 二级-基础-START 5-1 -->
          <el-submenu index="5-1">
            <template slot="title">
              <i class="el-icon-reading"></i>
              <span slot="title">{{$t('m.fed.basics.name')}}</span>
            </template>
            <el-menu-item index="5-1" @click="redirect('HTML')">{{$t('m.fed.basics.html')}}</el-menu-item>
            <el-menu-item index="5-5" @click="redirect('XML')">{{$t('m.fed.basics.xml')}}</el-menu-item>
            <el-menu-item index="5-10" @click="redirect('JSP')">{{$t('m.fed.basics.jsp')}}</el-menu-item>
            <el-menu-item index="5-15" @click="redirect('H5')">{{$t('m.fed.basics.h5')}}</el-menu-item>
            <el-menu-item index="5-20" @click="redirect('CSS')">{{$t('m.fed.basics.css')}}</el-menu-item>
            <el-menu-item index="5-25" @click="redirect('CSS-3')">{{$t('m.fed.basics.css3')}}</el-menu-item>
            <el-menu-item index="5-30" @click="redirect('JQuery')">{{$t('m.fed.basics.jquery')}}</el-menu-item>
          </el-submenu>
          <!-- 二级-基础-END -->
          <!-- 二级-框架-START 5-5 -->
          <el-submenu index="5-5">
            <template slot="title">
              <i class="el-icon-crop"></i>
              <span slot="title">{{$t('m.fed.framework.name')}}</span>
            </template>
            <!-- 三级-页面设计-START -->
            <el-submenu index="5-5-1">
              <template slot="title">
                <i class="el-icon-edit"></i>
                <span slot="title">{{$t('m.fed.framework.page_design.name')}}</span>
              </template>
              <el-menu-item index="5-5-1-1" @click="redirect('boostrap')">Boostrap</el-menu-item>
              <el-menu-item index="5-5-1-5" @click="redirect('element-ui')">Element UI</el-menu-item>
            </el-submenu>
            <!-- 三级-页面设计-END -->
            <!-- 三级-前端脚本-START -->
            <el-submenu index="5-5-5">
              <template slot="title">
                <i class="el-icon-edit-outline"></i>
                <span slot="title">{{$t('m.fed.framework.t_fe_s.name')}}</span>
              </template>
              <el-menu-item index="5-5-5-1" @click="redirect('vue')">VUE</el-menu-item>
            </el-submenu>
            <!-- 三级-前端脚本-END -->
          </el-submenu>
          <!-- 二级-框架-END -->
          <!-- 二级-开发工具-START 5-10 -->
          <el-submenu index="5-10">
            <template slot="title">
              <i class="el-icon-suitcase"></i>
              <span slot="title">{{$t('m.fed.development_tool.name')}}</span>
            </template>
            <el-menu-item index="1-1-3-1" @click="redirect('HBuilder')">HBuilder</el-menu-item>
            <el-menu-item index="1-1-3-2" @click="redirect('DW')">Adobe Dreamweaver</el-menu-item>
            <el-menu-item index="1-1-3-3" @click="redirect('vs_code')">Visual Studio Code</el-menu-item>
          </el-submenu>
          <!-- 二级-开发工具-END -->
        </el-submenu>
        <!-- 一级-前端开发-END -->
        <!-- 一级-后端开发-START 10 -->
        <el-submenu index="10">
          <template slot="title">
            <i class="el-icon-s-platform"></i>
            <span slot="title">{{$t('m.bed.name')}}</span>
          </template>
          <!-- 二级-基础-START 10-1 -->
          <el-submenu index="10-1">
            <template slot="title">
              <i class="el-icon-reading"></i>
              <span slot="title">{{$t('m.bed.basics.name')}}</span>
            </template>
            <el-menu-item index="10-1-1" @click="redirect('C')">C</el-menu-item>
            <el-menu-item index="10-1-5" @click="redirect('C++')">C++</el-menu-item>
            <el-menu-item index="10-1-10" @click="redirect('C#')">C#</el-menu-item>
            <el-menu-item index="10-1-15" @click="redirect('.NET')">.NET</el-menu-item>
            <el-menu-item index="10-1-20" @click="redirect('JAVA')">JAVA</el-menu-item>
            <el-menu-item index="10-1-25" @click="redirect('DOS')">DOS Command</el-menu-item>
          </el-submenu>
          <!-- 二级-基础-END -->
          <!-- 二级-框架-START 10-5 -->
          <el-submenu index="10-5">
            <template slot="title">
              <i class="el-icon-crop"></i>
              <span slot="title">{{$t('m.bed.framework.name')}}</span>
            </template>
            <el-menu-item index="10-5-1" @click="redirect('Maven')">Maven</el-menu-item>
            <el-menu-item index="10-5-5" @click="redirect('Struts')">Struts</el-menu-item>
            <el-menu-item index="10-5-10" @click="redirect('Struts-2')">Struts2</el-menu-item>
            <el-menu-item index="10-5-15" @click="redirect('Spring')">Spring</el-menu-item>
            <el-menu-item index="10-5-20" @click="redirect('MyBatis')">MyBatis</el-menu-item>
            <el-menu-item index="10-5-25" @click="redirect('spring_mvc')">Spring MVC</el-menu-item>
            <el-menu-item index="10-5-30" @click="redirect('spring_boot')">Spring Boot</el-menu-item>
          </el-submenu>
          <!-- 二级-框架-END -->
          <!-- 二级-系统-START 10-10 -->
          <el-submenu index="10-10">
            <template slot="title">
              <i class="el-icon-monitor"></i>
              <span slot="title">{{$t('m.bed.system.name')}}</span>
            </template>
            <el-menu-item index="10-10-1" @click="redirect('Linux')">Linux</el-menu-item>
            <el-menu-item index="10-10-5" @click="redirect('Uinux')">Uinux</el-menu-item>
            <el-menu-item index="10-10-10" @click="redirect('winxp')">Windows XP</el-menu-item>
            <el-menu-item index="10-10-15" @click="redirect('win7')">Windows 7</el-menu-item>
            <el-menu-item index="10-10-20" @click="redirect('win8')">Windows 8</el-menu-item>
            <el-menu-item index="10-10-25" @click="redirect('win10')">Windows 10</el-menu-item>
          </el-submenu>
          <!-- 二级-系统-END -->
          <!-- 二级-数据库-START 10-15 -->
          <el-submenu index="10-15">
            <template slot="title">
              <i class="el-icon-box"></i>
              <span slot="title">{{$t('m.bed.database.name')}}</span>
            </template>
            <!-- 三级-sql-START 10-15-1 -->
            <el-submenu index="10-15-1">
              <template slot="title">
                <i class="el-icon-sunrise-1"></i>
                <span slot="title">{{$t('m.bed.database.sql.name')}}</span>
              </template>
              <el-menu-item index="10-15-1-1" @click="redirect('Foxtable')">Foxtable</el-menu-item>
              <el-menu-item index="10-15-1-5" @click="redirect('SyBase')">SyBase</el-menu-item>
              <el-menu-item index="10-15-1-10" @click="redirect('MySQL')">MySQL</el-menu-item>
              <el-menu-item index="10-15-1-15" @click="redirect('SQLServer')">SQLServer</el-menu-item>
              <el-menu-item index="10-15-1-20" @click="redirect('ORACLE')">ORACLE</el-menu-item>
            </el-submenu>
            <!-- 三级-sql-END -->
            <!-- 三级-nosql-START 10-15-5 -->
            <el-submenu index="10-15-5">
              <template slot="title">
                <i class="el-icon-sunrise"></i>
                <span slot="title">{{$t('m.bed.database.nosql.name')}}</span>
              </template>
              <el-menu-item index="10-15-5-1" @click="redirect('Redis')">Redis</el-menu-item>
              <el-menu-item index="10-15-5-5" @click="redirect('MongDB')">MongDB</el-menu-item>
            </el-submenu>
            <!-- 三级-nosql-END -->
            <!-- 三级-开发工具-START 10-15-10 -->
            <el-submenu index="10-15-10">
              <template slot="title">
                <i class="el-icon-suitcase"></i>
                <span slot="title">{{$t('m.bed.database.development_tool.name')}}</span>
              </template>
              <el-menu-item index="10-15-5-1" @click="redirect('NaviCat')">NaviCat</el-menu-item>
              <el-menu-item index="10-15-5-5" @click="redirect('PowerDesigner')">PowerDesigner</el-menu-item>
              <el-menu-item index="10-15-5-10" @click="redirect('PLSQL')">PL/SQL Developer (PLSQL)</el-menu-item>
              <el-menu-item index="10-15-5-15" @click="redirect('SSMS')">SQL Server Management Studio (SSMS)</el-menu-item>
            </el-submenu>
            <!-- 三级-开发工具-END -->
          </el-submenu>
          <!-- 二级-数据库-END -->
          <!-- 二级-开发工具-START 10-20 -->
          <el-submenu index="10-20">
            <template slot="title">
              <i class="el-icon-suitcase"></i>
              <span slot="title">{{$t('m.bed.development_tool.name')}}</span>
            </template>
            <el-menu-item index="10-20-1" @click="redirect('Eclipse')">Eclipse</el-menu-item>
            <el-menu-item index="10-20-5" @click="redirect('MyEclipse')">MyEclipse</el-menu-item>
            <el-menu-item index="10-20-10" @click="redirect('IDEA')">IntelliJ IDEA</el-menu-item>
          </el-submenu>
          <!-- 二级-开发工具-END -->
          <!-- 二级-第三方接口-START -->
          <el-submenu index="10-25">
            <template slot="title">
              <i class="el-icon-news"></i>
              <span slot="title">{{$t('m.bed.t_p_o_i.name')}}</span>
            </template>
            <el-menu-item index="10-25-1" @click="redirect('QQ')">QQ</el-menu-item>
            <el-menu-item index="10-25-5" @click="redirect('Map')">{{$t('m.bed.t_p_o_i.map')}}</el-menu-item>
            <el-menu-item index="10-25-10" @click="redirect('WeChat')">{{$t('m.bed.t_p_o_i.wechat')}}</el-menu-item>
            <el-menu-item index="10-25-15" @click="redirect('Alipay')">{{$t('m.bed.t_p_o_i.alipay')}}</el-menu-item>
            <el-menu-item index="10-25-20" @click="redirect('Weather')">{{$t('m.bed.t_p_o_i.weather')}}</el-menu-item>
            <el-menu-item index="10-25-25" @click="redirect('Postbox')">{{$t('m.bed.t_p_o_i.postbox')}}</el-menu-item>
            <el-menu-item index="10-25-30" @click="redirect('Phone Number')">{{$t('m.bed.t_p_o_i.c_p_n')}}</el-menu-item>
            <el-menu-item index="10-25-35" @click="redirect('SMS')">{{$t('m.bed.t_p_o_i.sms')}}</el-menu-item>
          </el-submenu>
          <!-- 二级-第三方接口-END -->
        </el-submenu>
        <!-- 一级-后端开发-END -->
        <!-- 一级-二次元网址 -->
        <el-submenu index="15">
          <template slot="title">
            <i class="el-icon-s-promotion"></i>
            <span slot="title">{{$t('m.navigation.q_e.name')}}</span>
          </template>
          <el-submenu index="15-1">
            <template slot="title">
              <i class="el-icon-connection"></i>
              <span slot="title">{{$t('m.navigation.q_e.name')}}</span>
            </template>
            <el-menu-item index="15-1-0" @click="redirect('3d')">{{$t('m.navigation.q_e.3')}}</el-menu-item>
            <el-menu-item index="15-1-1" @click="redirect('AcFun')">{{$t('m.navigation.q_e.a')}}</el-menu-item>
            <el-menu-item index="15-1-5" @click="redirect('bilibili')">{{$t('m.navigation.q_e.b')}}</el-menu-item>
            <el-menu-item index="15-1-10" @click="redirect('CosZ')">{{$t('m.navigation.q_e.c')}}</el-menu-item>
            <el-menu-item index="15-1-15" @click="redirect('dilidili')">{{$t('m.navigation.q_e.d')}}</el-menu-item>
            <el-menu-item index="15-1-20" @click="redirect('E-hantai')">{{$t('m.navigation.q_e.e')}}</el-menu-item>
            <el-menu-item index="15-1-25" @click="redirect('FAKKU')">{{$t('m.navigation.q_e.f')}}</el-menu-item>
            <el-menu-item index="15-1-30" @click="redirect('Gelbooru')">{{$t('m.navigation.q_e.g')}}</el-menu-item>
            <el-menu-item index="15-1-35" @click="redirect('KonaChan')">{{$t('m.navigation.q_e.k')}}</el-menu-item>
            <el-menu-item index="15-1-40" @click="redirect('loli_flex')">{{$t('m.navigation.q_e.l')}}</el-menu-item>
            <el-menu-item index="15-1-45" @click="redirect('MissEvan')">{{$t('m.navigation.q_e.m')}}</el-menu-item>
            <el-menu-item index="15-1-50" @click="redirect('Pzhan')">{{$t('m.navigation.q_e.p')}}</el-menu-item>
            <el-menu-item index="15-1-55" @click="redirect('Pixiv')">{{$t('m.navigation.q_e.skip_p')}}</el-menu-item>
          </el-submenu>
        </el-submenu>
        <!-- 一级-二次元网址 -->
        <!-- 一级-国际化-START -->
        <el-submenu index="100">
          <template slot="title">
            <i class="el-icon-more"></i>
            <span slot="title">{{$t('m.Language.name')}}</span>
          </template>
          <el-menu-item index="100-1" @click="changeLangEvent('zh-CN')">{{$t('m.Language.chinese')}}</el-menu-item>
          <el-submenu index="100-5">
            <template slot="title">
              <i class="el-icon-brush"></i>
              <span slot="title">{{$t('m.Language.loading_force')}}</span>
            </template>
            <el-menu-item index="100-5" @click="changeLangEvent('en-US')">{{$t('m.Language.english')}}</el-menu-item>
            <el-menu-item index="100-10" @click="changeLangEvent('ja-JP')">{{$t('m.Language.japanese')}}</el-menu-item>
          </el-submenu>
        </el-submenu>
        <!-- 一级-国际化-END -->
    </el-menu>
  </div>
</template>

<script>
export default {
  name : 'left_aside',
  data() {
    return {
      isCollapse: true,
      paths: [
        /* 前端开发 基础 */
        {
          name: 'HTML',
          target: '_blank',
          path: 'https://www.w3school.com.cn/html/index.asp'
        },
        {
          name: 'XML',
          target: '_blank',
          path: 'https://www.w3school.com.cn/xml/index.asp'
        },
        {
          name: 'JSP',
          target: '_blank',
          path: 'https://www.w3cschool.cn/jsp/'
        },
        {
          name: 'H5',
          target: '_blank',
          path: 'https://www.runoob.com/html/html5-new-element.html'
        },
        {
          name: 'CSS',
          target: '_blank',
          path: 'https://www.w3school.com.cn/css/index.asp'
        },
        {
          name: 'CSS-3',
          target: '_blank',
          path: 'https://www.w3school.com.cn/css3/index.asp'
        },
        {
          name: 'JQuery',
          target: '_blank',
          path: 'https://jquery.com/'
        },
        /* 前端开发 框架 */
        {
          name: 'boostrap',
          target: '_blank',
          path: 'https://www.bootcss.com/'
        },
        {
          name: 'element-ui',
          target: '_blank',
          path: 'https://element.eleme.cn/#/zh-CN'
        },
        {
          name: 'vue',
          target: '_blank',
          path: 'https://vuejs.org/'
        },
        /* 前端开发 工具 */
        {
          name: 'HBuilder',
          target: '_blank',
          path: 'https://www.dcloud.io/'
        },
        {
          name: 'DW',
          target: '_blank',
          path: 'https://helpx.adobe.com/tw/dreamweaver/user-guide.html'
        },
        {
          name: 'vs_code',
          target: '_blank',
          path: 'https://code.visualstudio.com/'
        },
        /* 后端开发 基础 */
        {
          name: 'C',
          target: '_blank',
          path: 'https://www.runoob.com/cprogramming/c-tutorial.html'
        },
        {
          name: 'C++',
          target: '_blank',
          path: 'https://www.runoob.com/cplusplus/cpp-tutorial.html'
        },
        {
          name: 'C#',
          target: '_blank',
          path: 'https://www.runoob.com/csharp/csharp-tutorial.html'
        },
        {
          name: '.NET',
          target: '_blank',
          path: 'https://dotnet.microsoft.com/'
        },
        {
          name: 'JAVA',
          target: '_blank',
          path: 'https://www.runoob.com/java/java-tutorial.html'
        },
        {
          name: 'DOS',
          target: '_blank',
          path: 'https://www.w3cschool.cn/dosmlxxsc1/'
        },
        /* 后端开发 框架 */
        {
          name: 'Maven',
          target: '_blank',
          /* https://mvnrepository.com/ */
          path: 'https://www.runoob.com/maven/maven-tutorial.html'
        },
        {
          name: 'Struts',
          target: '_blank',
          path: 'https://struts.apache.org/index.html'
        },
        {
          name: 'Struts-2',
          target: '_blank',
          path: 'https://www.w3cschool.cn/struts_2/'
        },
        {
          name: 'Spring',
          target: '_blank',
          path: 'https://spring.io/'
        },
        {
          name: 'MyBatis',
          target: '_blank',
          path: 'https://mybatis.org/mybatis-3/'
        },
        {
          name: 'SpringMVC',
          target: '_blank',
          path: 'https://www.yiibai.com/spring_mvc/'
        },
        {
          name: 'Spring Boot',
          target: '_blank',
          path: 'https://spring.io/projects/spring-boot/'
        },
        /* 后端开发 系统 */
        {
          name: 'Linux',
          target: '_blank',
          path: 'https://www.runoob.com/linux/linux-tutorial.html'
        },
        {
          name: 'Uinux',
          target: '_blank',
          path: 'https://www.runoob.com/linux/linux-tutorial.html'
        },
        {
          name: 'winxp',
          target: '_blank',
          path: 'http://www.ghostw7.com/new/xp/'
        },
        {
          name: 'win7',
          target: '_blank',
          path: 'http://www.ghostw7.com/new/win7/'
        },
        {
          name: 'win8',
          target: '_blank',
          path: 'http://www.ghostw7.com/new/win8/'
        },
        {
          name: 'win10',
          target: '_blank',
          path: 'http://www.ghostw7.com/new/win10/'
        },
        /* 后端开发 SQL 数据库 */
        {
          name: 'Foxtable',
          target: '_blank',
          path: 'http://www.foxtable.com/'
        },
        {
          name: 'SyBase',
          target: '_blank',
          path: 'https://www.taodocs.com/p-246085119.html'
        },
        {
          name: 'MySQL',
          target: '_blank',
          path: 'https://www.runoob.com/mysql/mysql-tutorial.html'
        },
        {
          name: 'SQLServer',
          target: '_blank',
          path: 'https://www.w3school.com.cn/sql/index.asp'
        },
        {
          name: 'ORACLE',
          target: '_blank',
          path: 'https://www.w3cschool.cn/oraclejc/'
        },
        /* 后端开发 NOSQL 数据库 */
        {
          name: 'Redis',
          target: '_blank',
          path: 'https://redis.io/'
        },
        {
          name: 'MongDB',
          target: '_blank',
          path: 'https://www.runoob.com/mongodb/mongodb-tutorial.html'
        },
        /* 后端开发 数据库 - 工具 */
        {
          name: 'NaviCat',
          target: '_blank',
          path: 'https://www.navicat.com.cn/'
        },
        {
          name: 'PowerDesigner',
          target: '_blank',
          path: 'http://powerdesigner.de/en/'
        },
        {
          name: 'PLSQL',
          target: '_blank',
          path: 'https://www.oracle.com/database/technologies/appdev/plsql.html'
        },
        /* 后端开发 工具 */
        {
          name: 'Eclipse',
          target: '_blank',
          path: 'https://www.eclipse.org/downloads/'
        },
        {
          name: 'MyEclipse',
          target: '_blank',
          path: 'https://www.myeclipsecn.com/'
        },
        {
          name: 'IDEA',
          target: '_blank',
          path: 'http://www.jetbrains.com/'
        },
        /* 后端开发 第三方接口 */
        {
          name: 'QQ',
          target: '_blank',
          path:
            'https://wiki.open.qq.com/wiki/%E3%80%90QQ%E7%99%BB%E5%BD%95%E3%80%91API%E6%96%87%E6%A1%A3'
        },
        {
          name: 'Map',
          target: '_blank',
          path: 'http://lbsyun.baidu.com/index.php?title=jspopular'
        },
        {
          name: 'WeChat',
          target: '_blank',
          path:
            'https://developers.weixin.qq.com/doc/oplatform/Website_App/WeChat_Login/Wechat_Login.html'
        },
        {
          name: 'Alipay',
          target: '_blank',
          path: 'https://docs.open.alipay.com/api'
        },
        {
          name: 'Weather',
          target: '_blank',
          path: 'https://yq.aliyun.com/zt/49546'
        },
        {
          name: 'Postbox',
          target: '_blank',
          path: 'http://openmail.qq.com/'
        },
        {
          name: 'Phone Number',
          target: '_blank',
          path: 'http://www.114best.com/sdk.aspx'
        },
        {
          name: 'SMS',
          target: '_blank',
          path: 'https://mxt.molink.cn/mxt-jieshao?b_scene_zt=1'
        },
        /* 二次元 */
        {
          name: '3d',
          target: '_blank',
          path: 'http://konachan.wjcodes.com/index_3d.php'
        },
        {
          name: 'AcFun',
          target: '_blank',
          path: 'https://www.acfun.cn/'
        },
        {
          name: 'bilibili',
          target: '_blank',
          path: 'https://www.bilibili.com/'
        },
        {
          name: 'CosZ',
          target: '_blank',
          path: 'http://tucao.one/'
        },
        {
          name: 'dilidili',
          target: '_blank',
          path: 'http://bbs.005.tv/'
        },
        {
          name: 'E-hantai',
          target: '_blank',
          path: 'http://animehip.com/'
        },
        {
          name: 'FAKKU',
          target: '_blank',
          path: 'https://www.fakku.net/hentai/english'
        },
        {
          name: 'Gelbooru',
          target: '_blank',
          path: 'http://konachan.wjcodes.com/index_g.php'
        },
        {
          name: 'KonaChan',
          target: '_blank',
          path: 'http://konachan.wjcodes.com/'
        },
        {
          name: 'loli_flex',
          target: '_blank',
          path: 'http://konachan.wjcodes.com/index_loli_flex.php'
        },
        {
          name: 'MissEvan',
          target: '_blank',
          path: 'https://www.missevan.com/'
        },
        {
          name: 'Pzhan',
          target: '_blank',
          path: 'https://www.pzhan.com/'
        },
        {
          name: 'Pixiv',
          target: '_blank',
          path: 'https://pixivic.com/'
        }
      ]
    };
  },
  methods: {
    /* 当前选中项 */
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
    /* 跳转网页 */
    redirect(cost) {
      this.paths.forEach(e => {
        if (e.name == cost) {
          // transfer.$emit('child', e.path);
          window.open(e.path);
          return;
        }
      });
    },
    /* 国际化[切换语言] changeLangEvent({'zh_CN','en_US','ja_JP'}) */
    changeLangEvent(lang) {
      this.$i18n.locale = lang; // 切换关键语句
    }
  }
}
</script>

<style>
/* .el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
} */
</style>