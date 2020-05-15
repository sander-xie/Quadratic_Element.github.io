<template>
  <div class="homBox">
    <!-- <span v-text="$t('m.music')"></span> -->
    <!-- <span>{{$t('m.man')}}</span> -->
    <el-container>
      <!-- <el-aside> -->
        <left_aside />
      <!-- </el-aside> -->
      <el-container>
        <el-header height="60px"><input_field /></el-header>
        <!-- min-height: calc(100vh - 121px) -->
        <el-main> 
          <!-- <middle-iframe />  -->
          <photo_gallery /> 
        </el-main>
        <!-- style="margin-bottom: -130px" -->
        <el-footer height="60px" style="margin-bottom: -30px">
          <bottom />
        </el-footer>
      </el-container>
    </el-container>
    <!-- .page-component__scroll .el-scrollbar__wrap -->
    <el-backtop target=".homBox"></el-backtop>
  </div>
</template>

<script>
/* 直接引用 */
// import top from "@/components/portion/header";
export default {
  name: "home_page",
  data() {
    return {};
  },
  methods: {
  },
  components: {
    /* 懒加载 */
    // "middle-iframe": resolve =>
    //   require(["@/components/front/body/middle_iframe.vue"], resolve),
    top: resolve => require(['@/components/gm/header/top'], resolve),
    input_field: resolve => require(['@/components/gm/header/input_field'], resolve),
    left_aside: resolve => require(["@/components/gm/aside/left_aside.vue"], resolve),
    photo_gallery: resolve => require(["@/components/gm/body/photo_gallery.vue"], resolve),
    bottom: resolve => require(["@/components/gm/footer/bottom.vue"], resolve)
  }
}
</script>

<style>
  /* 隐藏滚动条 */
  ::-webkit-scrollbar {
    height: 0;
    width: 0 !important;
  }
body {
  margin: 0;
}
html,
body,
#app,
.homBox,
.el-container {
  padding: 0;
  margin: 0;
  background-color: Transparent;
  height: 130%;
}
.el-container > .el-header {
  background-color: rgb(255, 255, 255);
}
.el-container > .el-amin {
  background-color: rgb(69, 139, 209);
}
.el-container > .el-footer {
  /* background-color: rgb(84, 92, 100); */
  background-color: Transparent;
}
</style>