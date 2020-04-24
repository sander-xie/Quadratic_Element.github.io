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
                <font color="#909399" v-if="true">还在开发中！ 喵 o（＾∀＾）o !</font>
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
                <div class="right" @click="setting_popup_frame_reveal_method('open')">
                    <el-tooltip v-blink:visible="setting_hint_reveal" :content="setting_hint_content" class="item" effect="light" placement="right-end">
                        <!-- <el-button round> -->
                            <i class="el-icon-setting"></i>
                        <!-- </el-button> -->
                    </el-tooltip>
                </div>
            </el-col>
        </el-row>

        <!-- setting_popup_frame -->
        <el-dialog title="设置" :visible.sync="setting_popup_frame_reveal">
        <el-form v-model="setting_popup_frame_form" label-width="80px">
            <el-form-item label="设置按键提示文字是否显示" :label-width="formLabelWidth">
                <el-select v-model="setting_popup_frame_form.setting_hint_reveal" placeholder="请选择">
                    <el-option label="显示" value="false"></el-option>
                    <el-option label="隐藏" value="true"></el-option>
                </el-select>
            </el-form-item>
            <el-form-item label="设置按键提示文字修改ㅤㅤ" :label-width="formLabelWidth">
                <el-row :gutter="0">
                    <el-col :span="14" :offset="6">
                        <el-input type="text" v-model="setting_popup_frame_form.setting_hint_content" maxlength="20" show-word-limit width="50px" placeholder="请输入你想要的提示文字" clearable></el-input>
                    </el-col>
                </el-row>
            </el-form-item>
            <el-form-item label="搜索按钮提示文字是否显示" :label-width="formLabelWidth">
                <el-select v-model="setting_popup_frame_form.search_hint_reveal" placeholder="请选择">
                    <el-option label="显示" value="false"></el-option>
                    <el-option label="隐藏" value="true"></el-option>
                </el-select>
            </el-form-item>
            <el-form-item label="搜索按钮提示文字修改ㅤㅤ" :label-width="formLabelWidth">
                <el-row :gutter="0">
                    <el-col :span="14" :offset="6">
                        <el-input type="text" v-model="setting_popup_frame_form.search_hint_content" maxlength="20" show-word-limit width="50px" placeholder="请输入你想要的提示文字" clearable></el-input>
                    </el-col>
                </el-row>
            </el-form-item>
        </el-form>
            <div slot="footer" class="dialog-footer">
                <el-button @click="setting_popup_frame_reveal_method('abrogate')">取 消</el-button>
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
            /* 是否显示提示 */
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
            }]
        }
    },
    methods: {
        setting_popup_frame_reveal_method : function (directive) {
            if(directive=="open"){
                this.setting_popup_frame_reveal=true;
            }else if(directive=="save"){
                if(this.setting_popup_frame_form.setting_hint_reveal!=''){
                    this.setting_hint_reveal = this.setting_popup_frame_form.setting_hint_reveal;
                }
                if(this.setting_popup_frame_form.setting_hint_content!=''){
                    this.setting_hint_content = this.setting_popup_frame_form.setting_hint_content;
                }
                if(this.setting_popup_frame_form.search_hint_reveal!=''){
                    this.search_hint_reveal = this.setting_popup_frame_form.search_hint_reveal;
                }
                if(this.setting_popup_frame_form.search_hint_content!=''){
                    this.search_hint_content = this.setting_popup_frame_form.search_hint_content;
                }
                this.setting_popup_frame_reveal=false;
                // this.setting_hint_reveal = this.setting_popup_frame_form;
                // this.setting_hint_reveal = this.setting_popup_frame_form;
            }else if(directive=="abrogate"){
                this.setting_popup_frame_reveal=false;
            }
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