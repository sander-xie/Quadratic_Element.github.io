<template>
    <div>
        <el-row :gutter="20">
            <el-col :span="6">
                <el-select v-model="figure" placeholder="指定老婆查询">
                    <el-option
                    v-for="item in figure_list"
                    :key="item.value"
                    :label="item.Character_Name"
                    :value="item.another_name">
                        <el-tooltip :disabled="figure_hint_reveal" :content="item.presentation" class="item" effect="light" placement="right-end">
                            <div>
                                <span style="float: left">{{ item.Character_Name }}</span>
                                <span style="float: right; color: #8492a6; font-size: 13px">{{ item.another_name }}</span>
                            </div>
                        </el-tooltip>
                    </el-option>
                </el-select>
            </el-col>
            <el-col :span="4">
                <el-select v-model="resolution_ratio" placeholder="请选择图片大小">
                    <el-option
                    v-for="item in picture_size_list"
                    :key="item.value"
                    :label="item.format"
                    :value="item.size">
                        <el-tooltip :disabled="resolution_ratio_hint_reveal" :content="resolution_ratio_hint_content" class="item" effect="light" placement="right-end">
                            <div>
                                <span style="float: left">{{ item.format }}</span>
                                <span style="float: right; color: #8492a6; font-size: 13px">{{ item.size }}</span>
                            </div>
                        </el-tooltip>
                    </el-option>
                </el-select>
            </el-col>
            <el-col :span="5">
                <font color="#909399" v-if="true">程序员正在加急开发中!</font>
                <i class="el-icon-loading"></i>
            </el-col>
            <el-col :span="6"><el-input v-model="search_value" :placeholder="search_hint_placeholder"></el-input></el-col>
            <el-col :span="2">
                <div class="right">
                    <el-tooltip :disabled="search_hint_reveal" :content="search_hint_content" class="item" effect="light" placement="right-end">
                        <el-button round>
                            <i class="el-icon-search"></i>
                        </el-button>
                    </el-tooltip>
                </div>
            </el-col>
            <el-col :span="1">
                <div class="right" @click="method_setting_popup_frame_reveal('open')">
                    <el-tooltip :disabled="setting_hint_reveal" :content="setting_hint_content" class="item" effect="light" placement="right-end">
                        <!-- <el-button round> -->
                            <i class="el-icon-setting"></i>
                        <!-- </el-button> -->
                    </el-tooltip>
                </div>
            </el-col>
        </el-row>

        <!-- setting_popup_frame -->
        <el-dialog title="设置" :visible.sync="setting_popup_frame_reveal" destroy-on-close>
        <el-form :model="setting_popup_frame_form" label-width="80px">
            <el-form-item label="设置按键提示文字是否显示" :label-width="formLabelWidth">
                <el-checkbox v-model="setting_popup_frame_form.setting_hint_reveal" border>
                    <font v-if="setting_popup_frame_form.setting_hint_reveal">显示</font>
                    <font v-if="!setting_popup_frame_form.setting_hint_reveal">隐藏</font>
                </el-checkbox>
            </el-form-item>
            <el-form-item label="设置按键提示文字修改ㅤㅤ" :label-width="formLabelWidth">
                <el-row :gutter="0">
                    <el-col :span="18" :offset="4">
                        <el-input type="text" :disabled="!setting_popup_frame_form.setting_hint_reveal" v-model="setting_popup_frame_form.setting_hint_content" maxlength="20" show-word-limit width="50px" placeholder="请输入你想要的提示文字" clearable></el-input>
                    </el-col>
                </el-row>
            </el-form-item>
            <el-form-item label="搜索按钮提示文字是否显示" :label-width="formLabelWidth">
                <el-checkbox v-model="setting_popup_frame_form.search_hint_reveal" border>
                    <font v-if="setting_popup_frame_form.search_hint_reveal">显示</font>
                    <font v-if="!setting_popup_frame_form.search_hint_reveal">隐藏</font>
                </el-checkbox>
            </el-form-item>
            <el-form-item label="搜索按钮提示文字修改ㅤㅤ" :label-width="formLabelWidth">
                <el-row :gutter="0">
                    <el-col :span="18" :offset="4">
                        <el-input type="text" :disabled="!setting_popup_frame_form.search_hint_reveal" v-model="setting_popup_frame_form.search_hint_content" maxlength="20" show-word-limit width="50px" placeholder="请输入你想要的提示文字" clearable></el-input>
                    </el-col>
                </el-row>
            </el-form-item>
            <el-form-item label="搜索输入框提示文字修改ㅤ" :label-width="formLabelWidth">
                <el-row :gutter="0">
                    <el-col :span="18" :offset="4">
                        <el-input type="text" v-model="setting_popup_frame_form.search_hint_placeholder" maxlength="25" show-word-limit width="50px" placeholder="请输入你想要的提示文字" clearable></el-input>
                    </el-col>
                </el-row>
            </el-form-item>
            <el-form-item label="图片大小提示文字是否显示" :label-width="formLabelWidth">
                <el-checkbox v-model="setting_popup_frame_form.resolution_ratio_hint_reveal" border>
                    <font v-if="setting_popup_frame_form.resolution_ratio_hint_reveal">显示</font>
                    <font v-if="!setting_popup_frame_form.resolution_ratio_hint_reveal">隐藏</font>
                </el-checkbox>
            </el-form-item>
            <el-form-item label="老婆提示文字是否显示" :label-width="formLabelWidth">
                <el-checkbox v-model="setting_popup_frame_form.figure_hint_reveal" border>
                    <font v-if="setting_popup_frame_form.figure_hint_reveal">显示</font>
                    <font v-if="!setting_popup_frame_form.figure_hint_reveal">隐藏</font>
                </el-checkbox>
            </el-form-item>
        </el-form>
            <div slot="footer" class="dialog-footer">
                <el-button type="info" @click="default_settings();default_settings_hint()">默 认</el-button>
                <el-button type="info" @click="empty_settings();empty_settings_hint()">清 空</el-button>
            </div>
            <div slot="footer" class="dialog-footer">
                <el-button @click="method_setting_popup_frame_reveal('abrogate')">取 消</el-button>
                <el-button type="primary" @click="setting_popup_frame_reveal_method('save')">确 定</el-button>
            </div>
        </el-dialog>
        
    </div>

</template>

<script>
export default {
    name: 'input_field',
    data() {
        return {
            /* 是否隐藏提示 */
            setting_hint_reveal: false, /* 设置按键 */
            search_hint_reveal: false, /* 搜索按键 */
            resolution_ratio_hint_reveal: false, /* 图片分辨率 */
            figure_hint_reveal: false, /* 指定人物 */
            /* 提示内容 */
            setting_hint_content: '点我设置哦！ 喵 o（＾∀＾）o !', /* 设置按键 */
            search_hint_content: '点我查询哦！ 喵 o（＾∀＾）o !', /* 查询按钮 */
            search_hint_placeholder: '请不要输入特殊符号哦 ! 喵 o（＾∀＾）o !', /* 查询输入框 */
            resolution_ratio_hint_content: '点我！ 喵 o（＾∀＾）o !', /* 图片分辨率 */
            /* 选择、输入值 */
            search_value: "", /* 头部搜索栏输入值 */
            resolution_ratio: '', /* 图片分辨率 */
            figure: '', /* 指定人物 */
            /* 设置弹出框架 */
            setting_popup_frame_reveal: false, /* 是否显示提示 */
            formLabelWidth: '200px',
            setting_popup_frame_form: {
                setting_hint_reveal: '', /* 设置按键 */
                search_hint_reveal: '', /* 查询按钮 */
                resolution_ratio_hint_reveal: '', /* 图片分辨率 */
                setting_hint_content: '', /* 设置按键 */
                search_hint_content: '', /* 查询按钮 */
                search_hint_placeholder: '',/* 查询输入框 */
                resolution_ratio_hint_content: '', /* 图片分辨率 */
                figure_hint_reveal: '' /* 指定人物 */
            },
            /* 中转数据 */
            Transfer: {
                setting_hint_reveal: '', /* 设置按键 */
                setting_hint_content: '', /* 设置按键 */
                search_hint_reveal: '', /* 查询按钮 */
                search_hint_content: '', /* 查询按钮 */
                resolution_ratio_hint_reveal: '', /* 图片分辨率 */
                resolution_ratio_hint_content: '', /* 图片分辨率 */
                figure_hint_reveal: '' /* 指定人物 */
            },
            /* 数据源 */
            figure_list: [{
                Character_Name: '', /* 人物名称 */
                another_name: '', /* 别名 */
                alias: '', /* 化名 */
                presentation: '' /* 介绍 */
            }, {
                Character_Name: '香风智乃', 
                another_name: '智乃酱', 
                alias: '',
				presentation: '今天要来点兔子吗'
            }, {
                Character_Name: '春日野穹',
                another_name: '穹妹',
                alias: '',
                presentation: '缘之空'
            }],
            picture_size_list: [{
                format: '',
                size: ''
            }, {
                format: '私藏',
                size: '16 X 16'
            }, {
                format: '250P',
                size: '320 X 250'
            }, {
                format: '360P',
                size: '480 X 360'
            }, {
                format: '720P',
                size: '1280 X 800'
            }, {
                format: '1K',
                size: '1920 X 1080'
            }, {
                format: '2K',
                size: '2560 X 1440'
            }, {
                format: '3K',
                size: '3200 X 1800'
            }, {
                format: '4K',
                size: '3840 X 2160'
            }, {
                format: '5K',
                size: '5120 X 2880'
            }, {
                format: '8K',
                size: '7680 X 4320'
            }],
            /* 内置提示消息 */
            internally_installed_message: { }
        }
    },
    methods: {
        /* 同步数据获取 */
        synchronization_acquire : function (){
            /* 将当前按键值同步至中间值 */
            this.Transfer.setting_hint_reveal = this.setting_hint_reveal, /* 设置按键 */
            this.Transfer.search_hint_reveal = this.search_hint_reveal, /* 查询按钮 */
            this.Transfer.figure_hint_reveal = this.figure_hint_reveal, /* 指定人物 */
            this.Transfer.resolution_ratio_hint_reveal = this.resolution_ratio_hint_reveal, /* 图片分辨率 */
            this.Transfer.setting_hint_content = this.setting_hint_content, /* 设置按键 */
            this.Transfer.search_hint_content = this.search_hint_content, /* 查询按钮 */
            this.Transfer.search_hint_placeholder = this.search_hint_placeholder, /* 查询输入框 */
            this.Transfer.resolution_ratio_hint_content = this.resolution_ratio_hint_content/* 图片分辨率 */

            /* 将当前中间值同步至设置弹框值 */
            this.setting_popup_frame_form.setting_hint_reveal = !this.Transfer.setting_hint_reveal; /* 设置按键 */
            this.setting_popup_frame_form.search_hint_reveal = !this.Transfer.search_hint_reveal, /* 查询按钮 */
            this.setting_popup_frame_form.figure_hint_reveal = !this.Transfer.figure_hint_reveal, /* 指定人物 */
            this.setting_popup_frame_form.resolution_ratio_hint_reveal = !this.Transfer.resolution_ratio_hint_reveal, /* 图片分辨率 */
            this.setting_popup_frame_form.setting_hint_content = this.Transfer.setting_hint_content, /* 设置按键 */
            this.setting_popup_frame_form.search_hint_content = this.Transfer.search_hint_content, /* 查询按钮 */
            this.setting_popup_frame_form.search_hint_placeholder = this.Transfer.search_hint_placeholder, /* 查询输入框 */
            this.setting_popup_frame_form.resolution_ratio_hint_content = this.Transfer.resolution_ratio_hint_content/* 图片分辨率 */
        },
        /* 同步数据传出 */
        synchronization_outflow : function (){
            this.setting_hint_reveal = this.Transfer.setting_hint_reveal, /* 设置按键 */
            this.search_hint_reveal = this.Transfer.search_hint_reveal, /* 查询按钮 */
            this.resolution_ratio_hint_reveal = this.Transfer.resolution_ratio_hint_reveal, /* 图片分辨率 */
            this.figure_hint_reveal = this.Transfer.figure_hint_reveal, /* 指定人物 */
            this.setting_hint_content = this.Transfer.setting_hint_content, /* 设置按键 */
            this.search_hint_content = this.Transfer.search_hint_content, /* 查询按钮 */
            this.search_hint_placeholder = this.Transfer.search_hint_placeholder, /* 查询输入框 */
            this.resolution_ratio_hint_content = this.Transfer.resolution_ratio_hint_content /* 图片分辨率 */
        },
        /* 同步数据核对 */
        synchronization_verify : function () {
            /* 提示是否展示-核对数据 */
            if(this.setting_popup_frame_form.setting_hint_reveal!=this.Transfer.setting_hint_reveal){
                this.Transfer.setting_hint_reveal = this.setting_popup_frame_form.setting_hint_reveal;
            }/* 设置按键 */

            if(this.setting_popup_frame_form.search_hint_reveal!=this.Transfer.search_hint_reveal){
                this.Transfer.search_hint_reveal = this.setting_popup_frame_form.search_hint_reveal;
            }/* 查询按钮 */

            if(this.setting_popup_frame_form.resolution_ratio_hint_reveal!=this.Transfer.resolution_ratio_hint_reveal){
                this.Transfer.resolution_ratio_hint_reveal = this.setting_popup_frame_form.resolution_ratio_hint_reveal;
            }/* 图片分辨率 */

            if(this.setting_popup_frame_form.figure_hint_reveal!=this.Transfer.figure_hint_reveal){
                this.Transfer.figure_hint_reveal = this.setting_popup_frame_form.figure_hint_reveal;
            }/* 指定人物 */


            /* 提示文字-核对数据*/
            if(this.setting_popup_frame_form.setting_hint_content!=this.Transfer.setting_hint_content){
                this.Transfer.setting_hint_content = this.setting_popup_frame_form.setting_hint_content;
            }/* 设置按键 */

            if(this.setting_popup_frame_form.search_hint_content!=this.Transfer.search_hint_content){
                this.Transfer.search_hint_content = this.setting_popup_frame_form.search_hint_content;
            }/* 查询按钮 */

            if(this.setting_popup_frame_form.search_hint_placeholder!=this.Transfer.search_hint_placeholder){
                this.Transfer.search_hint_placeholder = this.setting_popup_frame_form.search_hint_placeholder;
            }/* 查询输入框 */

            if(this.setting_popup_frame_form.resolution_ratio_hint_content!=this.Transfer.resolution_ratio_hint_content){
                this.Transfer.resolution_ratio_hint_content = this.setting_popup_frame_form.resolution_ratio_hint_content;
            }/* 图片分辨率 */
        },
        /* 恢复默认 - 后续从后台获取 */
        default_settings : function () {
            this.setting_hint_reveal= false, /* 设置按键 */
            this.search_hint_reveal= false, /* 查询按钮 */
            this.resolution_ratio_hint_reveal= false, /* 图片分辨率 */
            this.figure_hint_reveal= false, /* 指定人物 */
            this.setting_hint_content= '点我设置哦！ 喵 o（＾∀＾）o !', /* 设置按键 */
            this.search_hint_content= '点我查询哦！ 喵 o（＾∀＾）o !', /* 查询按钮 */
            this.search_hint_placeholder= '请不要输入特殊符号哦 ! 喵 o（＾∀＾）o !', /* 查询输入框 */
            this.resolution_ratio_hint_content= '点我！ 喵 o（＾∀＾）o !' /* 图片分辨率 */
            this.synchronization_acquire();
        },
        empty_settings : function () {
            this.setting_popup_frame_form.setting_hint_reveal = false; /* 设置按键 */
            this.setting_popup_frame_form.search_hint_reveal = false, /* 查询按钮 */
            this.setting_popup_frame_form.figure_hint_reveal = false, /* 指定人物 */
            this.setting_popup_frame_form.resolution_ratio_hint_reveal = false, /* 图片分辨率 */
            this.setting_popup_frame_form.setting_hint_content = '', /* 设置按键 */
            this.setting_popup_frame_form.search_hint_content = '', /* 查询按钮 */
            this.setting_popup_frame_form.search_hint_placeholder = '', /* 查询输入框 */
            this.setting_popup_frame_form.resolution_ratio_hint_content = ''/* 图片分辨率 */
        },
        /* 数据纠正 */
        data_redress : function () {
            this.setting_popup_frame_form.setting_hint_reveal = !this.setting_popup_frame_form.setting_hint_reveal; /* 设置按键 */
            this.setting_popup_frame_form.search_hint_reveal = !this.setting_popup_frame_form.search_hint_reveal, /* 查询按钮 */
            this.setting_popup_frame_form.figure_hint_reveal = !this.setting_popup_frame_form.figure_hint_reveal, /* 指定人物 */
            this.setting_popup_frame_form.resolution_ratio_hint_reveal = !this.setting_popup_frame_form.resolution_ratio_hint_reveal /* 图片分辨率 */
        },
        /* 系统设置弹窗 */
        method_setting_popup_frame_reveal: function(directive){
            if(directive=="open"){
                /* 同步数据 */
                this.synchronization_acquire();
                this.setting_popup_frame_reveal=true;
            }else if(directive=="abrogate"){
                this.setting_popup_frame_reveal=false;
            }
        },
        setting_popup_frame_reveal_method : function (directive) {
            if(directive=="save"){
                /* 数据纠正 */
                this.data_redress();
                /* 数据核对 */
                this.synchronization_verify();
                /* 将设置中的数据同步 */
                this.synchronization_outflow();
            }
            this.setting_popup_frame_reveal=false;
        },
        /* 提示消息 */
        open_message(close,msg,genre) {
            this.$message({
                showClose: close,
                message: msg,
                type: genre
            });
        },
        /* 设置按键提示文字是否显示 提示 */
        setting_decide_hint(msg,whether){
            console.log('test');
            if(!whether){
                this.open_message(true,msg,);
            }
        },
        default_settings_hint(){
            this.open_message(true,'提示 设置已恢复默认!','success');
        },
        empty_settings_hint(){
            this.open_message(true,'警告 设置已清空!','error');
        }
    }
}
</script>

<style>
.el-input {
    margin-top: 2px;
}
/* .el-row{
    margin-top: 1%;
} */
</style>