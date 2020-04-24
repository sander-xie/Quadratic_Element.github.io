<template>
  <!-- <el-progress type="circle" :percentage="25"></el-progress> -->
  
  <!-- <el-button type="primary">
    <el-progress :percentage="10" status="success"></el-progress>
  </el-button> -->

  <div class="bottom">
    <el-row>
      <el-col :span="12">
        <!-- text-inside="true" -->
        <el-button type="text" @click="dialogVisible = true">项目信息</el-button>
      </el-col>
      <el-col :span="2">
        <el-link href="http://yunluo.xyz" target="_blank" type="info">作者首页</el-link>
      </el-col>
      <el-col :span="24">
        <div class="transition-box">Copyright xietao</div>
      </el-col>
    </el-row>
    <el-dialog title="项目信息"
      :visible.sync="dialogVisible"
      width="30%"
      :before-close="handleClose">
      <el-row>
        <el-col :span="6">项目名称：</el-col>
        <el-col :span="18"><font class="xmxx-font-color">二次元壁纸分享 | quadratic_element</font></el-col>
        <el-col :span="24">
          <font>当前项目进度:</font>
          <el-progress :percentage="1"></el-progress>
        </el-col>
        <el-col :span="24">
          <font>您对我们的评价:</font>
          <div class="transition-box"><el-rate v-model="value" show-text></el-rate></div>
        </el-col>
      </el-row>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>

</template>

<script>
export default {
    name: "bottom",
    data() {
      return {
        dialogVisible: false,
        value: ''
      };
    },
    methods: {
      handleClose(done) {
        this.$confirm('确认关闭？')
          .then(_ => {
            done();
          })
          .catch(_ => {});
      }
    }
}
</script>

<style>
.xmxx-font-color {
  color:#409EFF;
}
.el-progress__text {
  color:#409EFF;
}
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


.el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }


.el-footer {
  width: 100%;
}
/* .footer_main {
  margin-right: 15%;
  width: 100%;
  height: 100px;
  background-color: rgb(84, 92, 100);
} */
</style>