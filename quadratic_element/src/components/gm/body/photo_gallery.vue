<template>
<!-- <img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" class="image">
style="width: 100px; height: 100px"
:offset="index > 0 ? 2 : 0"
 -->
 
 <!-- <el-row>
    <el-col :span="6" v-for="(o, index) in 4" :key="o" :offset="index > 0 ? 2 : 0">
        <el-card shadow="hover" :body-style="{padding: '0px',width: '20%',height: '100px'}">
            <el-image fit="contain" :src="src"></el-image>
        </el-card>
    </el-col>
</el-row> -->
 
 <div>
    <el-row>
        <el-col :span="24">
            <div class="grid-content bg-purple-dark"></div>
        </el-col>
    </el-row>
    <el-row style="line-height: 0px;">
        <el-col :span="4">
            <!-- <div class="grid-content bg-purple"></div> -->
            <el-card :body-style="{ padding: '0px',height: '100%' }" shadow="hover">
                <!-- <el-image fit="none" style="width: 100px; height: 100px" src="https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg"></el-image> -->
                <picture_presentation :picture="picture" />
            </el-card>
        </el-col>
        <!-- <el-col :span="4" :offset="1">
            <el-card :body-style="{ padding: '0px' }">
                <img width="100%" src="https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg" class="image">
            </el-card>
        </el-col>
        <el-col :span="4" :offset="1">
            <el-card :body-style="{ padding: '0px' }">
                <img width="100%" src="https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg" class="image">
            </el-card>
        </el-col>
        <el-col :span="4" :offset="1">
            <el-card :body-style="{ padding: '0px' }">
                <img width="100%" src="https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg" class="image">
            </el-card>
        </el-col>
        <el-col :span="4" :offset="1">
            <el-card :body-style="{ padding: '0px' }">
                <img width="100%" src="https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg" class="image">
            </el-card>
        </el-col> -->
    </el-row>
    <el-row>
        <el-col :span="24">
            <div class="grid-content bg-purple-dark"></div>
        </el-col>
    </el-row>
 </div>

</template>

<script>
export default {
    name:'photo_gallery',
    data() {
        return {
            pictures_src: 'aaa',
            picture: {
                id:'1', /* 图片ID */
                /* 小窗口图片地址 */
                path: 'https://konachan.net/sample/437c0af28e72530e12a3f4891695e189/Konachan.com%20-%20305542%20sample.jpg',
                /* 图片下载链接 */
                download_link: 'https://konachan.net/sample/437c0af28e72530e12a3f4891695e189/Konachan.com%20-%20305542%20sample.jpg',
                /* 全图查看链接 */
                link_href: 'https://image.baidu.com/search/index?tn=baiduimage&ct=201326592&lm=-1&cl=2&ie=gb18030&word=%B6%FE%B4%CE%D4%AA-%B9%FA%C3%F1%C0%CF%C6%C5&fr=ala&ala=1&alatpl=adress&pos=0&hs=2&xthttps=111111',
                /* 图片预览 */
                total_graph_link: 'https://konachan.net/sample/437c0af28e72530e12a3f4891695e189/Konachan.com%20-%20305542%20sample.jpg',
                /* 加载失败提示 */
                picture_outline_error: '啊咧! 加载失败了'
            }
        };
    },
    methods: {
        download : function (){
            var elemIF = document.createElement("iframe");
              elemIF.src = "https://konachan.net/data/preview/d2/45/d2459502e99b6f779bec9b7719e9be7d.jpg";
              elemIF.style.display = "none";
            document.body.appendChild(elemIF);
        }
    },
    components:{
        picture_presentation: resolve => require(["@/components/gm/body/picture_presentation.vue"], resolve)
    }
}
</script>

<style>
  .el-row {
    margin-bottom: 20px;
    /* &:last-child {
      margin-bottom: 0;
    } */
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>