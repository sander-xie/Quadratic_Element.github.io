<template>
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

    <el-dialog title="项目信息" top="25px" :visible.sync="project_dialogVisible" :before-close="handleClose" :show-close="false" destroy-on-close>
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
          <font>您对我们评价：</font>
          <el-button type="primary" @click="project_detailed.user_evaluate.evaluate_submit_visible = true">点我前往评价</el-button>
        </el-col>
      </el-row>
      <span slot="footer" class="dialog-footer">
        <el-button @click="project_dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="project_dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>

    <!-- title="您对我的评价" -->
    <el-dialog width="35%" top="25px" :visible.sync="project_detailed.user_evaluate.evaluate_submit_visible" :show-close="false" append-to-body destroy-on-close>
      <el-steps simple :active="1" style="margin-top: -40px">
          <el-step title="填写" icon="el-icon-edit"></el-step>
          <el-step title="完成" icon="el-icon-success"></el-step>
          <el-step title="保存" icon="el-icon-success" description="填写完成后可以点击保存！确认无误后在进行提交！"></el-step>
          <el-step title="提交" icon="el-icon-upload" description="提交后将永远无法修改！请慎重！"></el-step>
      </el-steps>

      <el-form :model="project_detailed.user_evaluate" label-width="80px" style="margin-top: 10px">
        <el-form-item label="总ㅤ分ㅤ">
          <div style="margin-top: 5px;margin-left: 15px">
            <el-progress :stroke-width="30" :text-inside="true" :percentage="project_detailed.user_evaluate.percentage" :color="project_detailed.user_evaluate.evaluate_submit_visible.colors"></el-progress>
          </div>
        </el-form-item>
        <el-form-item label="备ㅤ注ㅤ">
          <span style="margin-top: 10px;margin-left: 25px;">一星等于一分</span>
        </el-form-item>

        <el-form-item label="加分">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-button icon="el-icon-plus" @click="increase"></el-button>
          </div>
        </el-form-item>

        <el-form-item label="整体布局">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="主ㅤ题ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="颜ㅤ色ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="文ㅤ字ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="实ㅤ用ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="个性化ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="体ㅤ验ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="权ㅤ限ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
        <el-form-item label="资ㅤ源ㅤ">
          <div class="transition-box" style="margin-top: 10px;margin-left: 25px">
            <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
          </div>
        </el-form-item>
      </el-form>

      <div slot="footer" class="dialog-footer" style="margin-bottom: 15px">
        <el-button type="success" @click="project_detailed.user_evaluate.evaluate_submit_visible = true">提交</el-button>
        <br />
      </div>
      <div slot="footer" class="dialog-footer">
        <el-button @click="project_detailed.user_evaluate.evaluate_submit_visible = false">取 消</el-button>
        <el-button type="primary" @click="project_detailed.user_evaluate.evaluate_submit_visible = true">保存</el-button>
      </div>
    </el-dialog>

    <!-- <user_evaluate /> -->
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
          rate_of_progress: 10,
          /* 用户体验评价 */
          user_evaluate: {
            evaluate: null,
            evaluate_submit_visible: false,
            percentage: 0,
            colors: [
              {color: '#f56c6c', percentage: 20},
              {color: '#e6a23c', percentage: 40},
              {color: '#5cb87a', percentage: 60},
              {color: '#1989fa', percentage: 80},
              {color: '#6f7ad3', percentage: 100}
            ]
          }
        },
      }
    },
    methods: {
      increase() {
        if (this.project_detailed.user_evaluate.percentage < 100) {
          this.project_detailed.user_evaluate.percentage += 5;
        }
      },
      estimate_verdict (evaluate) {
        switch(evaluate){
          case 1: console.log('极差？ 来来来！  你来说下哪里差了？  这种话怎么会从你的嘴巴里面说出来？');break;
          case 2: console.log('失望？ 什么功能让你这么失望？  来点改进的意见？');break;
          case 3: console.log('一般？ 是什么让你觉得一般？  来点改进的意见？');break;
          case 4: console.log('满意？ 就不能给个惊喜么？  还是有功能不够爽么？');break;
          case 5: console.log('哇偶！ 给满分的你一定是人见人爱，花见花开，汽车见了绕道开的万中无一的幸运儿！');break;
        }
      },
      /* 保存评价 */
      evaluate_save: function (bool) {
        if(bool){
          this.estimate_verdict(this.project_detailed.evaluate);
        }
      },
      /* 提交评价 */
      evaluate_submit: function (bool) {
        if(bool){
          alert(this.project_detailed.evaluate);
        }else{
          
        }
        this.project_detailed.evaluate_submit_visible = false;
      },
      handleClose(done) {
        this.$confirm('确认关闭？')
          .then(_ => {
            done();
            this.project_detailed.evaluate = null;
          })
          .catch(_ => {});
      }
    },
    components:{
        user_evaluate: resolve => require(["@/components/gm/footer/user_evaluate.vue"], resolve)
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