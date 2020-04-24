<template>
  <div class="homBox">
    <!-- <span v-text="$t('m.music')"></span> -->
    <!-- <span>{{$t('m.man')}}</span> -->
    <el-container>
      <!-- <el-aside> -->
        <left_aside />
      <!-- </el-aside> -->
      <el-container>
        <el-header><input_field /></el-header>
        <el-main> <!-- <middle-iframe /> --> </el-main>
        <el-footer height="10%"> <bottom /> </el-footer>
      </el-container>
    </el-container>
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
    bottom: resolve => require(["@/components/gm/footer/bottom.vue"], resolve)
  }
}
</script>

<style>
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
  height: 2000px;
}
.el-container > .el-header {
  background-color: rgb(255, 255, 255);
}
.el-container > .el-amin {
  background-color: rgb(69, 139, 209);
}
.el-container > .el-footer {
  background-color: rgb(84, 92, 100);
}
</style>