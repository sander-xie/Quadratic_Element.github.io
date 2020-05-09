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
                        <!-- <a :href="pictures.download_image_link" style="color: #409EFF;" :download="pictures.download_image_name"> -->
                            <i class="el-icon-download" @click="download_image()"></i>
                        <!-- </a> -->
                    </el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" v-clipboard:copy="pictures.share_link" v-clipboard:success="onCopy" v-clipboard:error="onError">
                        <i class="el-icon-share"></i>
                    </el-link>
                </el-col>
                <el-col :span="8" :offset="1" style="height: 25px">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 14px;" :href="pictures.wallpaper_link">
                        <font v-text="pictures.image_name"></font>
                    </el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" @click="Preview_DialogVisible=true;">
                        <i class="el-icon-view"></i>
                    </el-link>
                </el-col>
                <el-col :span="3" :offset="1">
                    <el-link type="primary" target="_blank" :underline="false" style="margin-top: 8px;" @click="detailed_information_DialogVisible=true;">
                        <i class="el-icon-warning-outline"></i>
                    </el-link>
                </el-col>
            </el-row>
        </div>

        <!-- 鼠标滚轮禁用 @mousewheel.prevent -->
        <el-dialog :title="pictures.image_name" top="25px" :visible.sync="Preview_DialogVisible" width="96%" center :fullscreen="false" :before-close-close="false" @open="stopSrcoll()" @close="openSrcoll()" destroy-on-close>
            <el-image fit="scale-down" style="margin-left: 23%;width: 53%" :src="pictures.total_graph_link">
                <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                    <i class="el-icon-picture-outline">{{pictures.picture_outline_error}}</i>
                </div>
            </el-image>
            <span slot="footer" class="dialog-footer">
                <el-button @click="Preview_DialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="Preview_DialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>

        <!-- :title="pictures.detailed_information.title" -->
        <el-dialog :title="pictures.detailed_information.title" :style="{backgroundRepeat: 'no-repeat',backgroundImage:'url('+pictures.detailed_information_backdrop+')'}" style="background-size: 100% 100%;opacity: 0.66;" top="40px" :visible.sync="detailed_information_DialogVisible" width="48%" center :fullscreen="false" :show-close="false" destroy-on-close>
            <!-- 设置弹窗背景 http://localhost:8884/static/Image_resources/wallpaper/505306.jpg -->
            <div class="index">
                <div class="pull-height animated" :style="{backgroundRepeat: 'no-repeat',backgroundImage:'url('+pictures.total_graph_link+')'}" style="background-size: 100% 100%;opacity: 0.88;">
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                                <font class="el-row_el-col_font_title">全 名</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.figure_baidu_link">
                                <font class="el-row_el-col_font_content" v-text="picture.detailed_information.full_name"></font>
                            </el-link>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">昵 称</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <font class="el-row_el-col_font_content" v-text="picture.detailed_information.nick_name"></font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">爱 称</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <font class="el-row_el-col_font_content" v-text="picture.detailed_information.pet_name"></font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">番剧名称</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.bangumi_baidu_link">
                                <font class="el-row_el-col_font_content" v-text="picture.detailed_information.bangumi"></font>
                            </el-link>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">图片贡献人</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.provide_people_link">
                                <font class="el-row_el-col_font_content" v-text="picture.detailed_information.provide_people"></font>
                            </el-link>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">图片贡献方式</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.ways_of_supply_link">
                                <font class="el-row_el-col_font_content" v-text="picture.detailed_information.ways_of_supply"></font>
                            </el-link>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_title.span" :offset="detailed_information_title.offset">
                            <font class="el-row_el-col_font_title">图片来源</font>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                        <el-col :span="detailed_information_content.span" :offset="detailed_information_content.offset">
                            <el-link type="primary" target="_blank" :underline="false" :href="pictures.detailed_information.source_link">
                                <font class="el-row_el-col_font_content" v-text="picture.detailed_information.source"></font>
                                <!-- <font class="el-row_el-col_font_content" v-text="picture.detailed_information.source_link"></font> -->
                            </el-link>
                        </el-col>
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                    <el-row :gutter="detailed_information_gutter">
                    </el-row>
                </div>
            </div>
            <span slot="footer" class="dialog-footer">
                <!-- <el-button @click="detailed_information_DialogVisible = false">取 消</el-button> -->
                <!-- <el-button type="primary" @click="detailed_information_DialogVisible = false">确 定</el-button> -->
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
            /* 人物详细信息弹窗标题文字设置 */
            detailed_information_title: { span: 23,offset: 1 },
            /* 人物详细信息弹窗内容文字设置 */
            detailed_information_content: { span: 20,offset: 5 },
            /* 每一个 <el-col></el-col> 的间隔 */
            detailed_information_gutter: 0,
            detailed_information_DialogVisible: false,
            Preview_DialogVisible: false,
            pictures: this.picture,
            message_alert_parameters: this.message_alert_parameter,
            message_alert_param: {
                duration: '3000',
                close: 'true',
                msg: '错误！没有消息啦！',
                type: 'info'
            }
        }
    },
    // watch: { // 监听data中弹层状态
    //     popupStatus (val) {
    //         if (val) {
    //             document.body.style.overflow = 'hidden'
    //             document.addEventListener('touchmove', preD, {passive: false}) // 禁止页面滑动
    //         } else {
    //             document.body.style.overflow = '' // 出现滚动条
    //             document.removeEventListener('touchmove', preD, {passive: false})
    //             }
    //         }
    // },
    build: {
        assetsPublicPath: '/',
        assetsSubDirectory: 'static'
    },
    methods: {
        download_image : function (){
            this.downLoad_file(
                null,
                this.pictures.download_image_link,
                this.pictures.download_image_name
            );
        },
        // params 参数 路径 文件名
        downLoad_file (params, url, title) {  
            this.$axios({  
                method: 'get',
                url,
                headers: {
                    'Content-Type': 'application/json'
                },
                data: params,
                responseType: 'arraybuffer'
            }).then(res => {
                let headers = res.headers;
                let blob = new Blob([res.data], {
                type: headers['content-type']
            });  
                let link = document.createElement('a');
                link.href = window.URL.createObjectURL(blob);
                if (!title) {
                    const fileName = headers['content-disposition'];
                    title = fileName.includes('filename=') ? fileName.split('=')[1] : '下载的表单文件';
                }
                link.download = title;
                link.click();
            });
        },
        stopSrcoll(){
            var mo=function(e){e.preventDefault();};
            document.body.style.overflow='hidden';
            document.addEventListener("touchmove",mo,false);//禁止页面滑动
        },
        openSrcoll(){
            var mo=function(e){e.preventDefault();};
            document.body.style.overflow='';//出现滚动条
            document.removeEventListener("touchmove",mo,false);
        },
        /* 复制成功时的回调函数 */
        onCopy (e) {
            this.message_alert_param.duration = this.message_alert_parameters.duration.two_ms;
            this.message_alert_param.showClose = this.message_alert_parameters.showClose.t;
            this.message_alert_param.msg = this.pictures.message_alert_parameters.full_name + "分享链接已复制到剪切板！";
            this.message_alert_param.type = this.message_alert_parameters.type.s;
            this.message_alert()
        },
        /* 复制失败时的回调函数 */
        onError (e) {
            this.message_alert_param.duration = this.message_alert_parameters.duration.two_ms;
            this.message_alert_param.showClose = this.message_alert_parameters.showClose.t;
            this.message_alert_param.msg = this.message_alert_parameters.showClose.t + "抱歉，复制失败！";
            this.message_alert_param.type = this.message_alert_parameters.type.e;
            this.message_alert();
        },
        message_alert : function (){
            this.$message({
                /* 显示时长 */
                duration: this.message_alert_param.duration,
                /* 显示关闭按键 */
                showClose: this.message_alert_param.showClose,
                /* 消息内容 */
                message: this.message_alert_param.msg,
                /* 消息类型 */
                type: this.message_alert_param.type
            });
        }
    },
    /* 获取父组件传出值 */
    props:['picture','message_alert_parameter'],
    created: function () {
    }
}
</script>

<style scoped>
.el-row > .el-col {
    position: relative;
}
.el-row_el-col_font_title {
    color: black;
    font-size: 19px;
    font-weight: bold;
}
.el-row_el-col_font_content {
    color: black;
    font-size: 18px;
    font-weight: bold;
}
/* .index {
    filter:alpha(Opacity=65);
    -moz-opacity:0.65;
    opacity: 0.65;
    background-image: url('https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg');
    background-size: 100% 100%;
    color: #000000
} */
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
/* 使用伪类选择器 ::-webkit-scrollbar ,兼容chrome和safari浏览器 */
    /* .outContainer::-webkit-scrollbar {  
        width:0 !important;   // remove scrollbar space
        background: transparent;  // optional: just make scrollbar invisible
    } */

    /* 兼容IE10+ */
    /* .outContainer { -ms-overflow-style: none; } */

    /* 但是firefox代码无效 */
    /* .outContainer { overflow: -moz-scrollbars-none; } */
</style>