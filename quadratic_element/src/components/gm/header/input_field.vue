<template>
    <el-row :gutter="20">
        <el-col :span="6">
            <el-select v-model="resolution_ratio" placeholder="指定老婆查询">
                <el-option
                v-for="item in Character_Name"
                :key="item.value"
                :label="item.label"
                :value="item.value">
                    <el-tooltip :disabled="disabled" :content="item.tooltip_content" class="item" effect="light" placement="right-end">
                        <div>
                            <span style="float: left">{{ item.label }}</span>
                            <span style="float: right; color: #8492a6; font-size: 13px">{{ item.value }}</span>
                        </div>
                    </el-tooltip>
                    <!-- <el-tooltip :disabled="disabled" content="点我！ 喵 o（＾∀＾）o !" class="item" effect="light" placement="right-end">
                    </el-tooltip> -->
                </el-option>
            </el-select>
        </el-col>
        <el-col :span="4">
            <el-select v-model="resolution_ratio" placeholder="请选择图片大小">
                <el-option
                v-for="item in cities"
                :key="item.value"
                :label="item.label"
                :value="item.value">
                    <el-tooltip :disabled="disabled" content="点我！ 喵 o（＾∀＾）o !" class="item" effect="light" placement="right-end">
                        <div>
                            <span style="float: left">{{ item.label }}</span>
                            <span style="float: right; color: #8492a6; font-size: 13px">{{ item.value }}</span>
                        </div>
                    </el-tooltip>
                    <!-- <el-tooltip :disabled="disabled" content="点我！ 喵 o（＾∀＾）o !" class="item" effect="light" placement="right-end">
                    </el-tooltip> -->
                </el-option>
            </el-select>
        </el-col>
        <el-col :span="6">
            <font color="#909399" v-if="true">还在开发中！ 喵 o（＾∀＾）o !</font>
            <i class="el-icon-loading"></i>
        </el-col>
        <el-col :span="6"><el-input v-model="search" placeholder="请不要输入特殊符号哦 ! 喵 o（＾∀＾）o !"></el-input></el-col>
        <el-col :span="2">
              <div class="right">
                <el-tooltip :disabled="disabled" content="点我查询哦！ 喵 o（＾∀＾）o !" class="item" effect="light" placement="right-end">
                    <el-button round>
                        <i class="el-icon-search"></i>
                    </el-button>
                </el-tooltip>
            </div>
        </el-col>
    </el-row>

</template>

<script>
export default {
    name: 'input_field',
    data() {
        return {
            search:"",
            Character_Name: [{
                label: '',
                value: '',
                tooltip: ''
            }, {
                label: '穹妹',
                value: '春日野穹',
                tooltip_content: '来自番剧-> 缘之空 德国骨科'
            }],
            cities: [{
                label: '',
                value: ''
            }, {
                label: '250P',
                value: '320 X 250'
            }, {
                label: '360P',
                value: '480 X 360'
            }, {
                label: '720P',
                value: '1280 X 800'
            }, {
                label: '1K',
                value: '1920 X 1080'
            }, {
                label: '2K',
                value: '2560 X 1440'
            }, {
                label: '3K',
                value: '3200 X 1800'
            }, {
                label: '4K',
                value: '3840 X 2160'
            }, {
                label: '5K',
                value: '5120 X 2880'
            }, {
                label: '8K',
                value: '7680 X 4320'
            }],
            resolution_ratio: ''
        }
    },
    methods: {
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