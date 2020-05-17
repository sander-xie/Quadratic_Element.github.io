<template>
  <div>
    <el-button type="primary" @click="project_detailed.user_evaluate.evaluate_submit_visible = true">点我前往评价</el-button>
    <el-drawer title="您对我们的评价" :visible.sync="project_detailed.user_evaluate.evaluate_submit_visible" direction="ltr" size="50%" :show-close="false">
        <el-container>
            <el-main>
                
                <div style="height: 100px;">
                    <!-- direction="vertical" -->
                    <!-- <el-steps simple :active="1">
                        <el-step title="填写" icon="el-icon-edit"></el-step>
                        <el-step title="完成" icon="el-icon-success" description="填写完成后可以点击保存！确认无误后在进行提交！"></el-step>
                        <el-step title="提交" icon="el-icon-upload" description="提交后将永远无法修改！请慎重！"></el-step>
                    </el-steps> -->
                </div>
                <div class="transition-box">
                    <el-rate v-model="project_detailed.evaluate" show-text></el-rate>
                </div>
            </el-main>
        </el-container>
    </el-drawer>
  </div>
</template>

<script>
export default {
    name: 'user_evaluate',
    data() {
        return {
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
                user_evaluate: {
                    evaluate: null,
                    evaluate_submit_visible: false
                }
            },
        }
    }

}
</script>

<style>

</style>