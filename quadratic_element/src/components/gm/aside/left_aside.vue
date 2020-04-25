<template>
  <div>
    <el-menu default-active="1-4-1" class="el-menu-vertical-demo" :collapse="isCollapse">
        <el-menu-item index="1" @click="isCollapse=!isCollapse">
          <i class="el-icon-s-unfold" v-if="isCollapse"></i>
          <i class="el-icon-s-fold" v-if="!isCollapse"></i>
          <span slot="title">模板一</span>
        </el-menu-item>
        <el-submenu index="5">
          <template slot="title">
          <i class="el-icon-location"></i>
          <span slot="title">{{$t('m.fed.name')}}</span>
          </template>
          <el-menu-item-group>
              <span slot="title">{{$t('m.fed.basics.name')}}</span>
              <el-menu-item index="5-1-1" @click="redirect('HTML')">HTML</el-menu-item>
              <el-menu-item index="5-1-5" @click="redirect('XML')">XML</el-menu-item>
              <el-menu-item index="5-1-10" @click="redirect('JSP')">JSP</el-menu-item>
              <el-menu-item index="5-1-15" @click="redirect('H5')">HTML 5</el-menu-item>
              <el-menu-item index="5-1-20" @click="redirect('CSS')">CSS</el-menu-item>
              <el-menu-item index="5-1-25" @click="redirect('CSS-3')">CSS 3</el-menu-item>
              <el-menu-item index="5-1-30" @click="redirect('JQuery')">JQuery</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="5-5">
            <template slot="title">
              <span slot="title">{{$t('m.fed.framework.name')}}</span>
            </template>
            <el-menu-item-group index="5-5-1">
              <template slot="title">{{$t('m.fed.framework.page_design.name')}}</template>
              <el-menu-item index="5-5-1-1" @click="redirect('boostrap')">Boostrap</el-menu-item>
              <el-menu-item index="5-5-1-5" @click="redirect('element-ui')">Element UI</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group>
              <template slot="title">
                <span slot="title">{{$t('m.fed.framework.t_fe_s.name')}}</span>
              </template>
              <el-menu-item index="5-10-5-1" @click="redirect('vue')">VUE</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="5-10">
            <template slot="title">
              <span slot="title">{{$t('m.fed.development_tool.name')}}</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1-3-1" @click="redirect('HBuilder')">HBuilder</el-menu-item>
              <el-menu-item index="1-1-3-2" @click="redirect('DW')">Adobe Dreamweaver</el-menu-item>
              <el-menu-item index="1-1-3-3" @click="redirect('vs_code')">Visual Studio Code</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
        </el-submenu>
    </el-menu>
    <br /><br />
    <el-menu default-active="1-4-1" class="el-menu-vertical-demo" :collapse="isCollapse">
        <el-menu-item index="1" @click="isCollapse=!isCollapse">
          <i class="el-icon-s-unfold" v-if="isCollapse"></i>
          <i class="el-icon-s-fold" v-if="!isCollapse"></i>
          <span slot="title">模板二</span>
        </el-menu-item>
        <el-submenu index="5-1">
          <template slot="title">
          <i class="el-icon-location"></i>
          <span slot="title">{{$t('m.fed.name')}}</span>
          </template>
          <el-submenu index="5-1-1">
            <template slot="title">{{$t('m.fed.basics.name')}}</template>
            <el-menu-item index="5-1-1" @click="redirect('HTML')">HTML</el-menu-item>
            <el-menu-item index="5-1-5" @click="redirect('XML')">XML</el-menu-item>
            <el-menu-item index="5-1-10" @click="redirect('JSP')">JSP</el-menu-item>
            <el-menu-item index="5-1-15" @click="redirect('H5')">HTML 5</el-menu-item>
            <el-menu-item index="5-1-20" @click="redirect('CSS')">CSS</el-menu-item>
            <el-menu-item index="5-1-25" @click="redirect('CSS-3')">CSS 3</el-menu-item>
            <el-menu-item index="5-1-30" @click="redirect('JQuery')">JQuery</el-menu-item>
          </el-submenu>
          <el-submenu index="5-5">
            <template slot="title">{{$t('m.fed.framework.name')}}</template>
            <el-submenu index="5-5-1">
              <template slot="title">{{$t('m.fed.framework.page_design.name')}}</template>
              <el-menu-item index="5-5-1-1" @click="redirect('boostrap')">Boostrap</el-menu-item>
              <el-menu-item index="5-5-1-5" @click="redirect('element-ui')">Element UI</el-menu-item>
            </el-submenu>
            <el-submenu index="5-5-5">
              <template slot="title">{{$t('m.fed.framework.t_fe_s.name')}}</template>
              <el-menu-item index="5-5-5-1" @click="redirect('vue')">VUE</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-submenu>
    </el-menu>
  </div>
</template>

<script>
export default {
  name : 'left_aside',
  data() {
    return {
    isCollapse: true
    };
  },
  methods: {
  }
}
</script>

<style>
/* .el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
} */
</style>