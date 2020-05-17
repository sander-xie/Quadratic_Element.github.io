<template>
  <div>
    <el-dialog title="设置" top="40px" :visible.sync="setting_popup_frame_reveal" :show-close="false" destroy-on-close>
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
            <el-form-item label="老婆提示文字是否显示ㅤㅤ" :label-width="formLabelWidth">
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
    name: 'setting_popup_frame'

}
</script>

<style>

</style>