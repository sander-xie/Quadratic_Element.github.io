<template>
    <div class="demo-image__preview" style="width: 100%; height: 100%">
        <el-image style="width: 100%; height: 100%" :src="pictures.path">
            <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                <i class="el-icon-picture-outline">{{pictures.picture_outline_error}}</i>
            </div>
        </el-image>
        <div class="bottom clearfix" style="margin-top: 7px;">
            <el-row :gutter="0">
                <el-col :span="7" style="margin-left:4px;">
                    <el-link type="primary" target="_blank" style="margin-top:12px;">
                        <!-- 需同该网站ip或域名才能下载 -->
                        <a :href="pictures.download_image_link" style="color: #409EFF;" :download="pictures.download_image_name">
                            <!-- <img src='/static/logo.png' class="img-circle" width="35px" style="" /> -->
                            <i class="el-icon-download"></i>
                        </a>
                    </el-link>
                </el-col>
                <el-col :span="7" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" :href="pictures.wallpaper_link" style="margin-top:19px;">{{pictures.image_name}}</el-link>
                </el-col>
                <el-col :span="7" :offset="1">
                    <i style="margin-top:12px;" @click="Preview_DialogVisible=true" class="el-icon-view"></i>
                </el-col>
            </el-row>
        </div>

        <!-- style="margin-top: -73px;margin-left: -46px;margin-bottom: 25px;margin-right: -61px;" -->
        <el-dialog :title="pictures.image_name" top="25px" :visible.sync="Preview_DialogVisible" width="96%" center :fullscreen="false" :show-close="false" destroy-on-close>
            <!-- <el-row style="width: 100%">
                <el-col :offset="6" style="width: 50%">
                </el-col>
            </el-row> -->

            <el-image fit="scale-down" style="width: 48%" :src="pictures.total_graph_link">
                <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                    <i class="el-icon-picture-outline">啊咧! 加载失败了</i>
                </div>
            </el-image>
            
            <span slot="footer" class="dialog-footer">
                <!-- <el-button @click="Preview_DialogVisible = false">取 消</el-button> -->
                <!-- <el-button type="primary" @click="Preview_DialogVisible = false">确 定</el-button> -->
            </span>
        </el-dialog>

    </div>
</template>

<script>

export default {
    name:'picture_presentation',
    data() {
        return {
            url: '',
            Preview_DialogVisible: false,
            pictures: this.picture
        }
    },
    build: {
        assetsPublicPath: '/',
        assetsSubDirectory: 'static'
    },
    methods: {

    },
    /* 获取父组件传出值 */
    props:['picture'],
    created: function () {

    }
}
</script>

<style>
   /* 隐藏滚动条 */
   /* ::-webkit-scrollbar {
     width: 0 !important;
   }
   ::-webkit-scrollbar {
     width: 0 !important;height: 0;
   } */
</style>