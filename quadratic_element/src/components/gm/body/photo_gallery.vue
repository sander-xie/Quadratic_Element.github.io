<template> 
 <div>
    <!-- <el-row>
        <el-col :span="24">
            <div class="grid-content bg-purple-dark"></div>
        </el-col>
    </el-row> -->
    <el-row style="line-height: 0px;">
        <el-col :span="4">
            <!-- <div class="grid-content bg-purple"></div> -->
            <el-card :body-style="{padding: '0px',height: '100%' }" @click="download()" shadow="hover">
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
                /* 图片名称 */
                image_name: '香风智乃',
                /* 加载失败提示 */
                picture_outline_error: '啊咧! 加载失败了',
                /* 略缩图地址 */
                path: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                /* 下载图片名称 */
                download_image_name: 'quadratic_element-wallpaper-00001.jpg',
                /* 下载图片链接 */
                download_image_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                /* 分享图片链接 */
                share_link: 'http://localhost:8884/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                /* 全图查看链接 */
                wallpaper_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                /* 图片预览 */
                total_graph_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                /* 弹窗背幕壁纸 */
                detailed_information_backdrop: 'http://localhost:8884/static/Image_resources/wallpaper/505306.jpg',
                /* 详细信息弹窗 */
                detailed_information: {
                    /* 弹窗标题 */
                    title: 'じっと見ないで、変態',
                    /* 全名 */
                    full_name: '香风智乃',
                    /* 人物百度百科 */
                    figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                    /* 英文名 */
                    english_name: 'Cafe Style',
                    /* 日文名 */
                    japanese_name: 'かふう ちの',
                    /* 昵称 */
                    nick_name: '智乃',
                    /* 爱称 */
                    pet_name: '智乃酱',
                    /* 番剧名称 */
                    bangumi: '请问您今天要来点兔子吗？',
                    /* 番剧百度百科链接 */
                    bangumi_baidu_link: 'https://baike.baidu.com/item/%E8%AF%B7%E9%97%AE%E6%82%A8%E4%BB%8A%E5%A4%A9%E8%A6%81%E6%9D%A5%E7%82%B9%E5%85%94%E5%AD%90%E5%90%97%EF%BC%9F/5327974?fr=aladdin',
                    /* 漫画在线观看链接 */
                    caricature: 'https://manhua.dmzj.com/qwnjtyldtzm/',
                    /* 樱花动漫在线观看链接 */
                    primrose_animation_online_to_watch: 'http://www.imomoe.in/view/2492.html',
                    /* 图片提供人 */
                    provide_people: 'this website author',
                    /* 图片提供人主页 */
                    provide_people_link: 'http://localhost:8884',
                    /* 图片提供方式 */
                    ways_of_supply: '后台上传',
                    /* 图片提供入口 */
                    ways_of_supply_link: 'http://localhost:8884',
                    /* 图片来源 */
                    source: 'K站 Konachan-CHS',
                    /* 图片来源链接 */
                    source_link: 'https://konachan.net/sample/b07496edaf042e99b90bb0f77fc1c3ef/Konachan.com%20-%20305360%20sample.jpg?0.26283345924835855'
                }
            }
        };
    },
    build: {
        assetsPublicPath: '/',
        assetsSubDirectory: 'static'
    },
    methods: {
        download : function (){
            var elemIF = document.createElement("iframe");
              elemIF.src = "http://localhost:8884/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg";
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