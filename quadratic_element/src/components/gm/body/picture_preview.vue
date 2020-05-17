<template>
  <div>
    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" @click="Preview_DialogVisible=true;">
        <i class="el-icon-view"></i>
    </el-link>
    <el-drawer :title="pictures.image_name" direction="ltr" size="69%" :visible.sync="Preview_DialogVisible" :withHeader="false" destroy-on-close>
        <!-- <el-row>
            <el-col :span="18" style="background-color: #EBEEF5" @click="Preview_DialogVisible=false"> -->
                <img style="margin-top: 40px" height="574px" :src="pictures.total_graph_link" :alt="pictures.picture_outline_error">
                <!-- <el-image fit="scale-down" style="height: 643px;background-color: #F2F6FC;" :src="pictures.total_graph_link">
                    <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                        <i class="el-icon-picture-outline">
                            {{pictures.picture_outline_error}}
                        </i>
                    </div>
                </el-image> -->
            <!-- </el-col>
            <el-col :span="5" :offset="1" style="background-color: #EBEEF5">
                hhh
            </el-col> -->
        <!-- </el-row> -->
    </el-drawer>
    <el-drawer :title="pictures.image_name" direction="rtl" size="30.8%" :modal="false" :visible.sync="Preview_DialogVisible" :withHeader="true" destroy-on-close>
        <div style="height: 500px;width: 100%;">
            <happy-scroll color="rgba(0,0,0,0.5)" size="5" resize>
                <div>
                    <el-row>
                        <el-col></el-col>
                    </el-row>
                    <el-row>
                        <el-col :span="6">
                            <span>特征：</span>
                        </el-col>
                        <el-col :span="18">
                            <el-color-picker></el-color-picker>
                        </el-col>
                    </el-row>
                    <el-row>
                        <el-col>
                            <span style="font-size: 14px">miyase_mahiro</span>
                            <span style="font-size: 14px">></span>
                            <span style="font-size: 14px">画师</span>
                        </el-col>
                    </el-row>
                    <el-row>
                        <el-col>
                            <span style="font-size: 14px">温馨提示：按下Esc键或点击图片可以快速退出图片预览</span>
                        </el-col>
                    </el-row>
                    <el-row>
                        <el-col></el-col>
                    </el-row>
                </div>
            </happy-scroll>
        </div>
    </el-drawer>

    <!-- 鼠标滚轮禁用 @mousewheel.prevent :title="pictures.image_name" width="96%" -->
        <!-- <el-dialog  top="25px" :visible.sync="Preview_DialogVisible" width="96%" center :fullscreen="false" :before-close-close="false" @open="stopSrcoll()" @close="openSrcoll()" :show-close="false" destroy-on-close>
            <div style="margin-top: -55px;margin-left: -25px;position: absolute;owerflow: scroll;background-color: #EBEEF5;">
                <img style="margin: 18px" height="574px" :src="pictures.total_graph_link" :alt="pictures.picture_outline_error">
            </div>
        </el-dialog> -->
                    <!-- <div style="height: 574px;margin-top: -55px;margin-left: 555px;position: absolute;owerflow: scroll;background-color: #EBEEF5;">
                        <img style="margin: 18px" height="574px" :src="pictures.total_graph_link" :alt="pictures.picture_outline_error">
                    </div> -->
                    <!-- background-color: #F2F6FC; -->
                    <!-- <el-image fit="scale-down" style="margin-left: -300px;height: 576px;position: absolute;owerflow: scroll;" :src="pictures.total_graph_link">
                        <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                            <i class="el-icon-picture-outline">
                                {{pictures.picture_outline_error}}
                            </i>
                        </div>
                    </el-image> -->
                <!-- </el-col>
                <el-col :span="5" :offset="1" style="background-color: #EBEEF5">
                    hhh
                </el-col>
            </el-row> -->
        <!-- :with-header="false" -->
  </div>
</template>

<script>
export default {
    name: 'picture_preview',
    data() {
        return {
            Preview_DialogVisible: false
        }
    },
    props:['pictures']

}
</script>

<style>

</style>