<template>
    <div class="demo-image__preview" style="width: 100%; height: 100%" >
        <el-image style="width: 100%; height: 100%" :src="pictures.path" :href="pictures.wallpaper_link">
            <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                <i class="el-icon-picture-outline">{{pictures.picture_outline_error}}</i>
            </div>
        </el-image>
        <div class="bottom clearfix" style="margin-top: 11px;">
            <el-row :gutter="0">
                <el-col :span="3">
                    <el-link type="primary" target="_blank" style="margin-top: 8px;">
                        <!-- 需同该网站ip或域名才能下载 -->
                        <a :href="pictures.download_image_link" style="color: #409EFF;" :download="pictures.download_image_name">
                            <i class="el-icon-download"></i>
                        </a>
                    </el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" v-clipboard:copy="pictures.share_link" v-clipboard:success="onCopy" v-clipboard:error="onError"><i class="el-icon-share"></i></el-link>
                </el-col>
                <el-col :span="8" :offset="1" style="height: 25px">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 14px;" :href="pictures.wallpaper_link"><font v-text="pictures.image_name"></font></el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" @click="Preview_DialogVisible=true;stop()"><i class="el-icon-view"></i></el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" @click="detailed_information_DialogVisible=true;"><i class="el-icon-warning-outline"></i></el-link>
                </el-col>
            </el-row>
        </div>

        <!-- 鼠标滚轮禁用 @mousewheel.prevent -->
        <el-dialog :title="pictures.image_name" top="25px" :visible.sync="Preview_DialogVisible" width="96%" center :fullscreen="false" :show-close="false" destroy-on-close>
            <el-image fit="scale-down" style="width: 53%" :src="pictures.total_graph_link">
                <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                    <i class="el-icon-picture-outline">{{pictures.picture_outline_error}}</i>
                </div>
            </el-image>
            <span slot="footer" class="dialog-footer">
                <el-button @click="Preview_DialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="Preview_DialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>

        <el-dialog :title="pictures.image_name" top="60px" :visible.sync="detailed_information_DialogVisible" width="28%" center :fullscreen="false" :show-close="false" destroy-on-close>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>全 名</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.full_name"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>昵 称</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.nick_name"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>爱 称</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.pet_name"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>番剧名称</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.bangumi"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>图片提供人</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.provide_people"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>图片提供方式</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.ways_of_supply"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>图片来源</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7"><font v-text="picture.detailed_information.source"></font></el-col>
            </el-row>
            <el-row :gutter="0">
                <!-- <el-col :span="24"></el-col> -->
            </el-row>
            <el-row :gutter="0">
                <el-col :span="21" :offset="3"><font>图片来源链接</font></el-col>
            </el-row>
            <el-row :gutter="0">
                <el-col :span="17" :offset="7">
                    <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.source_link">
                        <font v-text="picture.detailed_information.source_link"></font>
                    </el-link>
                </el-col>
            </el-row>
            <span slot="footer" class="dialog-footer">
                <el-button @click="detailed_information_DialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="detailed_information_DialogVisible = false">确 定</el-button>
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
            detailed_information_DialogVisible: false,
            Preview_DialogVisible: false,
            pictures: this.picture
        }
    },
    build: {
        assetsPublicPath: '/',
        assetsSubDirectory: 'static'
    },
    methods: {
        stop(){
            var mo=function(e){e.preventDefault();};
            document.body.style.overflow='hidden';
            document.addEventListener("touchmove",mo,false);//禁止页面滑动
        },
        /* 复制成功时的回调函数 */
        onCopy (e) {
            this.$message.success("内容已复制到剪切板！")
        },
        /* 复制失败时的回调函数 */
        onError (e) {
            this.$message.error("抱歉，复制失败！")
        }
    },
    /* 获取父组件传出值 */
    props:['picture'],
    created: function () {
    }
}
</script>

<style scoped>

/* .el-col{
    border:1px solid red;
    text-align: center;
} */
   /* 隐藏滚动条 */
   /* ::-webkit-scrollbar {
     width: 0 !important;
   }
   ::-webkit-scrollbar {
     width: 0 !important;height: 0;
   } */
</style>