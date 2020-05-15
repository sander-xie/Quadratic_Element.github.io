<template>
  <!-- <el-progress type="circle" :percentage="25"></el-progress> -->
  
  <!-- <el-button type="primary">
    <el-progress :percentage="10" status="success"></el-progress>
  </el-button> -->

  <div class="bottom">
    <el-row>
      <el-col :span="10" :offset="1">
        <!-- text-inside="true" -->
        <div class="transition-box">Copyright xietao</div>
      </el-col>
      <!-- <el-col :span="2">
        <el-link href="http://yunluo.xyz" target="_blank" type="info">作者首页</el-link>
      </el-col> -->
      <el-col :span="10" :offset="1">
        <el-button type="text" @click="project_dialogVisible = true">项目信息</el-button>
      </el-col>
    </el-row>

    <el-dialog title="项目信息" :visible.sync="project_dialogVisible" top="50px" :before-close="handleClose" destroy-on-close>
      <el-row>
        <el-col :span="6">项目名称：</el-col>
        <el-col :span="18"><font class="xmxx-font-color">{{project_detailed.name}}</font></el-col>
      </el-row>
      <el-row>
        <el-col :span="6">版本信息：</el-col>
        <el-col :offset="18"></el-col>
        <el-col :span="12">当前状态：<font class="xmxx-font-color">{{project_detailed.version.state}}</font></el-col>
        <el-col :span="12">版本号：<font class="xmxx-font-color">{{project_detailed.version.build_no}}</font></el-col>
      </el-row>
      <el-row>
        <el-col :span="6">
          <font>项目进度：</font>
        </el-col>
        <el-col :offset="4" :span="20">
          <el-progress :percentage="project_detailed.rate_of_progress"></el-progress>
        </el-col>
      </el-row>
      <el-row>
        <el-col :span="24">
          <font>您对我的评价：</font>
          <el-popconfirm
            confirmButtonText='是的'
            :onConfirm="estimate(true)"
            cancelButtonText='让我在想想'
            icon="el-icon-info"
            iconColor="#f90"
            title="确定提交吗？">
          </el-popconfirm>
          <div class="transition-box" @click="estimate()"><el-rate v-model="project_detailed.evaluate" show-text></el-rate></div>
        </el-col>
      </el-row>
      <span slot="footer" class="dialog-footer">
        <el-button @click="project_dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="project_dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>

</template>

<script>
export default {
    name: "bottom",
    data() {
      return {
        /* 项目详细信息展示 */
        project_dialogVisible: false,
        /* 项目详细信息 */
        project_detailed: {
          name: '二次元壁纸分享ㅤ|ㅤquadratic_element',
          /* 版本信息 */
          version: {
            state: '内部开发中',
            build_no: '0.0.0.1'
          },
          /* 项目进度 */
          rate_of_progress: 1,
          /* 用户体验评价 */
          evaluate: null
        },
      };
    },
    methods: {
      estimate_verdict (evaluate) {
        switch(evaluate){
          case 1: console.log('呜呜呜？');break;
          case 2: console.log('这么少？');break;
          case 3: console.log('理由呢？');break;
          case 4: console.log('为啥不是满分？');break;
          case 5: console.log('这就对了嘛？');break;
          default: console.log('666 居然点出BUG了！');;break;
        }
      },
      estimate: function (bool) {
        if(bool){
          this.estimate_verdict(this.project_detailed.evaluate);
        }else{
          console.log('大哥，快点给我个满分啦！');
        }
      },
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
    /* &:last-child {
      margin-bottom: 0;
    } */
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