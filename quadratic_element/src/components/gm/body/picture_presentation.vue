<template>
    <div class="demo-image__preview" style="width: 100%; height: 100%">
        <el-image style="width: 100%; height: 100%" :src="pictures.path">
            <div slot="error" style="width: 100%; height: 100%" class="image-slot">
                <i class="el-icon-picture-outline">啊咧! 加载失败了</i>
            </div>
        </el-image>
        <div class="bottom clearfix" style="margin-top: 7px;">
            <el-row :gutter="0">
                <el-col :span="7" style="margin-left:4px;">
                    <el-link type="primary" target="_blank" :href="pictures.download_link" style="margin-top:12px;">
                        <i class="el-icon-download"></i>
                    </el-link>
                </el-col>
                <el-col :span="7" :offset="1">
                    <el-link type="primary" target="_blank" :href="pictures.link_href" style="margin-top:18px;">国民老婆</el-link>
                </el-col>
                <el-col :span="7" :offset="1">
                    <i style="margin-top:12px;" class="el-icon-view"></i>
                </el-col>
            </el-row>
        </div>

        <el-dialog title="提示" :visible.sync="centerDialogVisible" width="30%" center>
            <span>需要注意的是内容是默认不居中的</span>
            <span slot="footer" class="dialog-footer">
                <el-button @click="centerDialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="centerDialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>

    </div>
</template>

<script>
export default {
    name:'picture_presentation',
    data() {
        return {
            centerDialogVisible: false,
            pictures: this.picture
        }
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

</style>