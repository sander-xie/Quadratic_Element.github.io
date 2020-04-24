<template>
  <!-- class="el-menu-vertical-demo" -->
  <div>
    <!-- style="margin-bottom: 20px;" -->
    <!-- <el-radio-group v-model="isCollapse" >
      <el-radio-button :label="false">展开</el-radio-button>
      <el-radio-button :label="true">收起</el-radio-button>
    </el-radio-group> -->
    <el-menu
      :default-active="activeIndex2"
      class="el-menu-demo"
      text-color="#fff"
      background-color="#545c64"
      active-text-color="#ffd04b"
      mode="horizontal"
      @select="handleSelect"
      :collapse="isCollapse"
    >
      <el-submenu index="1">
        <template slot="title">{{$t('m.fed.name')}}</template>
        <el-submenu index="1-1">
          <template slot="title">{{$t('m.fed.basics.name')}}</template>
          <el-menu-item index="1-1-1" @click="redirect('HTML')">HTML</el-menu-item>
          <el-menu-item index="1-1-2" @click="redirect('XML')">XML</el-menu-item>
          <el-menu-item index="1-1-3" @click="redirect('JSP')">JSP</el-menu-item>
          <el-menu-item index="1-1-4" @click="redirect('H5')">HTML 5</el-menu-item>
          <el-menu-item index="1-1-5" @click="redirect('CSS')">CSS</el-menu-item>
          <el-menu-item index="1-1-6" @click="redirect('CSS-3')">CSS 3</el-menu-item>
          <el-menu-item index="1-1-7" @click="redirect('JQuery')">JQuery</el-menu-item>
        </el-submenu>

        <el-submenu index="1-2">
          <template slot="title">{{$t('m.fed.framework.name')}}</template>
          <el-submenu index="1-2-1">
            <template slot="title">{{$t('m.fed.framework.page_design.name')}}</template>
            <el-menu-item index="1-2-1-1" @click="redirect('boostrap')">Boostrap</el-menu-item>
            <el-menu-item index="1-2-1-2" @click="redirect('element-ui')">Element UI</el-menu-item>
          </el-submenu>
          <el-submenu index="1-2-2">
            <template slot="title">{{$t('m.fed.framework.t_fe_s.name')}}</template>
            <el-menu-item index="1-2-2-1" @click="redirect('vue')">VUE</el-menu-item>
          </el-submenu>
        </el-submenu>

        <el-submenu index="1-1-3">
          <template slot="title">{{$t('m.fed.development_tool.name')}}</template>
          <el-menu-item index="1-1-3-1" @click="redirect('HBuilder')">HBuilder</el-menu-item>
          <el-menu-item index="1-1-3-2" @click="redirect('DW')">Adobe Dreamweaver</el-menu-item>
          <el-menu-item index="1-1-3-3" @click="redirect('vs_code')">Visual Studio Code</el-menu-item>
        </el-submenu>
      </el-submenu>

      <el-submenu index="2">
        <template slot="title">{{$t('m.bed.name')}}</template>
        <el-submenu index="2-1">
          <template slot="title">{{$t('m.bed.basics.name')}}</template>
          <el-menu-item index="2-1-1" @click="redirect('C')">C</el-menu-item>
          <el-menu-item index="2-1-2" @click="redirect('C++')">C++</el-menu-item>
          <el-menu-item index="2-1-3" @click="redirect('C#')">C#</el-menu-item>
          <el-menu-item index="2-1-4" @click="redirect('.NET')">.NET</el-menu-item>
          <el-menu-item index="2-1-5" @click="redirect('JAVA')">JAVA</el-menu-item>
          <el-menu-item index="2-1-6" @click="redirect('DOS')">DOS Command</el-menu-item>
        </el-submenu>

        <el-submenu index="2-2">
          <template slot="title">{{$t('m.bed.framework.name')}}</template>
          <el-menu-item index="2-2-1" @click="redirect('Maven')">Maven</el-menu-item>
          <el-menu-item index="2-2-2" @click="redirect('Struts')">Struts</el-menu-item>
          <el-menu-item index="2-2-3" @click="redirect('Struts-2')">Struts2</el-menu-item>
          <el-menu-item index="2-2-4" @click="redirect('Spring')">Spring</el-menu-item>
          <el-menu-item index="2-2-5" @click="redirect('MyBatis')">MyBatis</el-menu-item>
          <el-menu-item index="2-2-6" @click="redirect('spring_mvc')">Spring MVC</el-menu-item>
          <el-menu-item index="2-2-7" @click="redirect('spring_boot')">Spring Boot</el-menu-item>
        </el-submenu>

        <el-submenu index="2-3">
          <template slot="title">{{$t('m.bed.system.name')}}</template>
          <el-menu-item index="2-3-1" @click="redirect('Linux')">Linux</el-menu-item>
          <el-menu-item index="2-3-2" @click="redirect('Uinux')">Uinux</el-menu-item>
          <el-menu-item index="2-3-3" @click="redirect('winxp')">Windows XP</el-menu-item>
          <el-menu-item index="2-3-4" @click="redirect('win7')">Windows 7</el-menu-item>
          <el-menu-item index="2-3-5" @click="redirect('win8')">Windows 8</el-menu-item>
          <el-menu-item index="2-3-6" @click="redirect('win10')">Windows 10</el-menu-item>
        </el-submenu>

        <el-submenu index="2-4">
          <template slot="title">{{$t('m.bed.database.name')}}</template>
          <el-submenu index="2-4-1">
            <template slot="title">{{$t('m.bed.database.sql.name')}}</template>
            <el-menu-item index="2-4-1-1" @click="redirect('Foxtable')">Foxtable</el-menu-item>
            <el-menu-item index="2-4-1-2" @click="redirect('SyBase')">SyBase</el-menu-item>
            <el-menu-item index="2-4-1-3" @click="redirect('MySQL')">MySQL</el-menu-item>
            <el-menu-item index="2-4-1-4" @click="redirect('SQLServer')">SQLServer</el-menu-item>
            <el-menu-item index="2-4-1-5" @click="redirect('ORACLE')">ORACLE</el-menu-item>
          </el-submenu>

          <el-submenu index="2-4-2">
            <template slot="title">{{$t('m.bed.database.nosql.name')}}</template>
            <el-menu-item index="2-4-2-1" @click="redirect('Redis')">Redis</el-menu-item>
            <el-menu-item index="2-4-2-2" @click="redirect('MongDB')">MongDB</el-menu-item>
          </el-submenu>

          <el-submenu index="2-4-3">
            <template slot="title">{{$t('m.bed.database.development_tool.name')}}</template>
            <el-menu-item index="2-4-3-1" @click="redirect('NaviCat')">NaviCat</el-menu-item>
            <el-menu-item index="2-4-3-2" @click="redirect('PowerDesigner')">PowerDesigner</el-menu-item>
            <el-menu-item index="2-4-3-3" @click="redirect('PLSQL')">PL/SQL Developer (PLSQL)</el-menu-item>
            <el-menu-item
              index="2-4-3-4"
              @click="redirect('SSMS')"
            >SQL Server Management Studio (SSMS)</el-menu-item>
          </el-submenu>
        </el-submenu>

        <el-submenu index="2-5">
          <template slot="title">{{$t('m.bed.development_tool.name')}}</template>
          <el-menu-item index="2-5-1" @click="redirect('Eclipse')">Eclipse</el-menu-item>
          <el-menu-item index="2-5-2" @click="redirect('MyEclipse')">MyEclipse</el-menu-item>
          <el-menu-item index="2-5-3" @click="redirect('IDEA')">IntelliJ IDEA</el-menu-item>
        </el-submenu>

        <el-submenu index="2-6">
          <template slot="title">{{$t('m.bed.t_p_o_i.name')}}</template>
          <el-menu-item index="2-6-1" @click="redirect('QQ')">QQ</el-menu-item>
          <el-menu-item index="2-6-2" @click="redirect('Map')">{{$t('m.bed.t_p_o_i.map')}}</el-menu-item>
          <el-menu-item index="2-6-3" @click="redirect('WeChat')">{{$t('m.bed.t_p_o_i.wechat')}}</el-menu-item>
          <el-menu-item index="2-6-4" @click="redirect('Alipay')">{{$t('m.bed.t_p_o_i.alipay')}}</el-menu-item>
          <el-menu-item index="2-6-5" @click="redirect('Weather')">{{$t('m.bed.t_p_o_i.weather')}}</el-menu-item>
          <el-menu-item index="2-6-6" @click="redirect('Postbox')">{{$t('m.bed.t_p_o_i.postbox')}}</el-menu-item>
          <el-menu-item index="2-6-7" @click="redirect('Phone Number')">{{$t('m.bed.t_p_o_i.c_p_n')}}</el-menu-item>
          <el-menu-item index="2-6-8" @click="redirect('SMS')">{{$t('m.bed.t_p_o_i.sms')}}</el-menu-item>
        </el-submenu>
      </el-submenu>

      <el-submenu index="3">
        <template slot="title">{{$t('m.q_e.name')}}</template>
        <el-menu-item index="3-1" @click="redirect('AcFun')">{{$t('m.q_e.a')}}</el-menu-item>
        <el-menu-item index="3-2" @click="redirect('bilibili')">{{$t('m.q_e.b')}}</el-menu-item>
        <el-menu-item index="3-3" @click="redirect('CosZ')">{{$t('m.q_e.c')}}</el-menu-item>
        <el-menu-item index="3-4" @click="redirect('dilidili')">{{$t('m.q_e.d')}}</el-menu-item>
        <el-menu-item index="3-5" @click="redirect('E-hantai')">{{$t('m.q_e.e')}}</el-menu-item>
        <el-menu-item index="3-6" @click="redirect('FAKKU')">{{$t('m.q_e.f')}}</el-menu-item>
        <el-menu-item index="3-7" @click="redirect('Gelbooru')">{{$t('m.q_e.g')}}</el-menu-item>
        <el-menu-item index="3-8" @click="redirect('MissEvan')">{{$t('m.q_e.m')}}</el-menu-item>
        <el-menu-item index="3-9" @click="redirect('KonaChan')">{{$t('m.q_e.k')}}</el-menu-item>
        <el-menu-item index="3-10" @click="redirect('Pzhan')">{{$t('m.q_e.p')}}</el-menu-item>
      </el-submenu>

      <el-menu-item index="4" disabled><i class="el-icon-document"></i>{{$t('m.being_developed.name')}}</el-menu-item>

      <el-menu-item index="5"><i class="el-icon-document"></i>{{survival_time}}</el-menu-item>
      <el-menu-item index="6"><i class="el-icon-document"></i>{{countdown_to_survival}}</el-menu-item>
      <el-menu-item index="7"><i class="el-icon-document"></i>{{this_time}}</el-menu-item>

      <el-menu-item index="8" @click="isCollapse=!isCollapse"><i class="el-icon-document"></i>隐藏</el-menu-item>

      <el-menu-item index="9">
        <el-submenu index="9-1">
          <template slot="title">{{$t('m.Language.name')}}</template>
          <el-menu-item index="9-1-1" @click="changeLangEvent('zh-CN')">{{$t('m.Language.chinese')}}</el-menu-item>
          <el-menu-item index="9-1-2" @click="changeLangEvent('en-US')">{{$t('m.Language.english')}}</el-menu-item>
        </el-submenu>
      </el-menu-item>


      <!-- <el-menu-item index="10" disabled>{{$t('m.i_t_c.name')}}</el-menu-item> -->
    </el-menu>
  </div>
</template>

<script>
// import { setInterval, clearInterval } from 'timers';
// import transfer from '@/router/transfer.js';
export default {
  name: 'top',
  data() {
    return {
      isCollapse: false,
      sonWord: '子组件传值',
      activeIndex: '1',
      activeIndex2: '1',
      timer: '',
      this_time: '',
      survival_time: '',
      countdown_to_survival: '',
      /* 账号 */
      pim_accoun_info: {
        ID: '1',
        Account: '1648183267',
        Password: 'woshixietao122334',
        Remember: '0',
        Status: '异常禁用',
        Grade: 'max',
        creation_time: '2019-11-29 13:43:10',
        Remark: 'Creater Account'
      },
      /* 账号关联用户 */
      pim_accoun_info_user_info: {
        ID: '1',
        accoun_info_ID: '1',
        user_info_ID: '1'
      },
      /* 用户 */
      pim_user_info: {
        ID: '1',
        name: '仰望氵星空',
        spell: 'yangwangshuixingkong',
        sex: '女',
        age: '23',
        phone: '15574367986',
        address: '云南文山州文山市',
        position: 'IT 实施工程师',
        remarks: '暂无'
      },
      /* 身份证 */
      pim_identity_card: {
        ID: '1',
        identity_Id: '430221200012022610',
        name: '谢涛',
        sex: '男',
        nation: '汉族',
        birth: '2000-12-02 22:18:56',
        address: '湖南省株洲县平山乡白鱼村掌型组28号',
        issuing_authority: '株洲县公安局',
        useful_life: '2016-11-11',
        adynamic_stage: '2021-11-11'
      },
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
          path: 'http://konachan.wjcodes.com/'
        },
        {
          name: 'MissEvan',
          target: '_blank',
          path: 'https://www.missevan.com/'
        },
        {
          name: 'KonaChan',
          target: '_blank',
          path: 'http://konachan.wjcodes.com/'
        },
        {
          name: 'Pzhan',
          target: '_blank',
          path: 'https://www.pzhan.com/'
        }
      ]
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
    redirect(cost) {
      this.paths.forEach(e => {
        if (e.name == cost) {
          // transfer.$emit('child', e.path);
          window.open(e.path);
          return;
        }
      });
    },
    /* 切换语言 */
    changeLangEvent(lang) {
      this.$i18n.locale = lang; // 关键语句
    },
    show_this_time() {
      var date = new Date();
      // var year = date.getFullYear(); // 得到当前年份
      // var month = date.getMonth() + 1; // 得到当前月份
      // var day = date.getDate(); // 得到当前几号
      var hour = date.getHours(); // 得到当前小时
      var min = date.getMinutes(); // 得到当前分钟
      var seconds = date.getSeconds(); // 得到当前秒
      if (hour < 10) {
        var hour = '0' + hour;
      }
      if (min < 10) {
        var min = '0' + min;
      }
      if (seconds < 10) {
        var seconds = '0' + seconds;
      }
      this.this_time = hour + ' : ' + min + ' : ' + seconds;
    }
  },
  mounted() {
    this.timer = setInterval(this.show_this_time, 1000);
  },
  destroyed() {
    clearInterval(this.timer);
  }
};
</script>

<style>
.el-header,
.el-footer {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
}

.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
.el-menu-demo {
  margin: 0;
  padding: 0;
}
</style>