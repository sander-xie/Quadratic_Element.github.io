<template> 
 <div>
    <!-- <el-row>
        <el-col :span="24">
            <div class="grid-content bg-purple-dark"></div>
        </el-col>
    </el-row> -->
    <!-- border: '1px solid #43B6BA' -->
    <el-row style="line-height: 0px;margin-top: -8px" :gutter="20">
        <div v-for="(picture) in pictures" :key="picture.id" class="text item">
            <!-- margin-left: 17px;margin-right: 36px; -->
            <el-col :span="4" style="margin-top: 8px;margin-bottom: 5px">
                <el-card :body-style="{padding: '0px',margin: '0px',height: '100%',width: '100%'}" shadow="hover">
                    <picture_presentation :picture="picture" :message_alert_parameter="message_alert_parameter" />
                </el-card>
            </el-col>
        </div>
    </el-row>

    <!-- <el-row :gutter="20">
        <el-col :span="24">
            <div class="grid-content bg-purple-dark"></div>
        </el-col>
    </el-row> -->
 </div>

</template>

<script>
export default {
    name:'photo_gallery',
    data() {
        return {
            pictures_src: 'aaa',
            /* 图片信息 */
            pictures: [
                {
                    id: 1, /* 图片ID */
                    /* 图片名称 */
                    image_name: '香风智乃',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                    /* 下载图片名称 */
                    download_image_name: 'quadratic_element-wallpaper-00001.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
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
                },
                {
                    id: '2', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00002.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00002.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00002.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00002.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00002.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00002.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '3', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00003.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00002.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00003.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00003.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00003.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00003.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '4', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00004.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00002.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00004.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00004.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00004.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00004.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '5', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00005.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00002.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00005.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00005.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00005.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00005.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '6', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00006.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00002.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00006.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00006.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00006.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00006.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '7', /* 图片ID */
                    /* 图片名称 */
                    image_name: '樱岛麻衣',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00007.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00007.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00007.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00007.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00007.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00007.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '樱岛麻衣',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E6%A8%B1%E5%B2%9B%E9%BA%BB%E8%A1%A3',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'さくらじま まい',
                        /* 昵称 */
                        nick_name: '师娘',
                        /* 爱称 */
                        pet_name: '麻衣学姐',
                        /* 番剧|游戏名称 */
                        bangumi: '青春猪头少年不会梦见兔女郎学姐',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                },
                {
                    id: '8', /* 图片ID */
                    /* 图片名称 */
                    image_name: '枣可萝',
                    /* 加载失败提示 */
                    picture_outline_error: '啊咧! 加载失败了',
                    /* 略缩图地址 */
                    path: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00008.jpg',
                    /* 下载图片名称 */
                    download_image_name: '00008.jpg',
                    /* 下载图片链接 */
                    download_image_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00008.jpg',
                    /* 分享图片链接 */
                    share_link: 'http://www.qe8884.top/static/Image_resources/wallpaper/quadratic_element-wallpaper-00008.jpg',
                    /* 全图查看链接 */
                    wallpaper_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00008.jpg',
                    /* 图片预览 */
                    total_graph_link: './static/Image_resources/wallpaper/quadratic_element-wallpaper-00008.jpg',
                    /* 弹窗背幕壁纸 */
                    detailed_information_backdrop: './static/Image_resources/wallpaper/505306.jpg',
                    /* 详细信息弹窗 */
                    detailed_information: {
                        /* 弹窗标题 */
                        title: 'じっと見ないで、変態',
                        /* 全名 */
                        full_name: '枣可萝',
                        /* 人物百度百科 */
                        figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
                        /* 英文名 */
                        english_name: 'Cafe Style',
                        /* 日文名 */
                        japanese_name: 'コッコロ',
                        /* 昵称 */
                        nick_name: '可可罗',
                        /* 爱称 */
                        pet_name: '妈',
                        /* 番剧名称 */
                        bangumi: '公主连结Re:Dive（プリンセスコネクト！Re:Dive）',
                        /* 番剧百度百科链接 */
                        bangumi_baidu_link: '',
                        /* 漫画在线观看链接 */
                        caricature: '',
                        /* 樱花动漫在线观看链接 */
                        primrose_animation_online_to_watch: '',
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
                        source_link: ''
                    }
                }
            ],
            // pictures: {
            //     picture: {
            //         id:'1', /* 图片ID */
            //         /* 图片名称 */
            //         image_name: '香风智乃',
            //         /* 加载失败提示 */
            //         picture_outline_error: '啊咧! 加载失败了',
            //         /* 略缩图地址 */
            //         path: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 下载图片名称 */
            //         download_image_name: 'quadratic_element-wallpaper-00001.jpg',
            //         /* 下载图片链接 */
            //         download_image_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 分享图片链接 */
            //         share_link: 'http://localhost:8884/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 全图查看链接 */
            //         wallpaper_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 图片预览 */
            //         total_graph_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 弹窗背幕壁纸 */
            //         detailed_information_backdrop: 'http://localhost:8884/static/Image_resources/wallpaper/505306.jpg',
            //         /* 详细信息弹窗 */
            //         detailed_information: {
            //             /* 弹窗标题 */
            //             title: 'じっと見ないで、変態',
            //             /* 全名 */
            //             full_name: '香风智乃',
            //             /* 人物百度百科 */
            //             figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
            //             /* 英文名 */
            //             english_name: 'Cafe Style',
            //             /* 日文名 */
            //             japanese_name: 'かふう ちの',
            //             /* 昵称 */
            //             nick_name: '智乃',
            //             /* 爱称 */
            //             pet_name: '智乃酱',
            //             /* 番剧名称 */
            //             bangumi: '请问您今天要来点兔子吗？',
            //             /* 番剧百度百科链接 */
            //             bangumi_baidu_link: 'https://baike.baidu.com/item/%E8%AF%B7%E9%97%AE%E6%82%A8%E4%BB%8A%E5%A4%A9%E8%A6%81%E6%9D%A5%E7%82%B9%E5%85%94%E5%AD%90%E5%90%97%EF%BC%9F/5327974?fr=aladdin',
            //             /* 漫画在线观看链接 */
            //             caricature: 'https://manhua.dmzj.com/qwnjtyldtzm/',
            //             /* 樱花动漫在线观看链接 */
            //             primrose_animation_online_to_watch: 'http://www.imomoe.in/view/2492.html',
            //             /* 图片提供人 */
            //             provide_people: 'this website author',
            //             /* 图片提供人主页 */
            //             provide_people_link: 'http://localhost:8884',
            //             /* 图片提供方式 */
            //             ways_of_supply: '后台上传',
            //             /* 图片提供入口 */
            //             ways_of_supply_link: 'http://localhost:8884',
            //             /* 图片来源 */
            //             source: 'K站 Konachan-CHS',
            //             /* 图片来源链接 */
            //             source_link: 'https://konachan.net/sample/b07496edaf042e99b90bb0f77fc1c3ef/Konachan.com%20-%20305360%20sample.jpg?0.26283345924835855'
            //         }
            //     },
            //     picture: {
            //         id:'1', /* 图片ID */
            //         /* 图片名称 */
            //         image_name: '香风智乃',
            //         /* 加载失败提示 */
            //         picture_outline_error: '啊咧! 加载失败了',
            //         /* 略缩图地址 */
            //         path: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 下载图片名称 */
            //         download_image_name: 'quadratic_element-wallpaper-00001.jpg',
            //         /* 下载图片链接 */
            //         download_image_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 分享图片链接 */
            //         share_link: 'http://localhost:8884/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 全图查看链接 */
            //         wallpaper_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 图片预览 */
            //         total_graph_link: '/static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg',
            //         /* 弹窗背幕壁纸 */
            //         detailed_information_backdrop: 'http://localhost:8884/static/Image_resources/wallpaper/505306.jpg',
            //         /* 详细信息弹窗 */
            //         detailed_information: {
            //             /* 弹窗标题 */
            //             title: 'じっと見ないで、変態',
            //             /* 全名 */
            //             full_name: '香风智乃',
            //             /* 人物百度百科 */
            //             figure_baidu_link: 'https://baike.baidu.com/item/%E9%A6%99%E9%A3%8E%E6%99%BA%E4%B9%83',
            //             /* 英文名 */
            //             english_name: 'Cafe Style',
            //             /* 日文名 */
            //             japanese_name: 'かふう ちの',
            //             /* 昵称 */
            //             nick_name: '智乃',
            //             /* 爱称 */
            //             pet_name: '智乃酱',
            //             /* 番剧名称 */
            //             bangumi: '请问您今天要来点兔子吗？',
            //             /* 番剧百度百科链接 */
            //             bangumi_baidu_link: 'https://baike.baidu.com/item/%E8%AF%B7%E9%97%AE%E6%82%A8%E4%BB%8A%E5%A4%A9%E8%A6%81%E6%9D%A5%E7%82%B9%E5%85%94%E5%AD%90%E5%90%97%EF%BC%9F/5327974?fr=aladdin',
            //             /* 漫画在线观看链接 */
            //             caricature: 'https://manhua.dmzj.com/qwnjtyldtzm/',
            //             /* 樱花动漫在线观看链接 */
            //             primrose_animation_online_to_watch: 'http://www.imomoe.in/view/2492.html',
            //             /* 图片提供人 */
            //             provide_people: 'this website author',
            //             /* 图片提供人主页 */
            //             provide_people_link: 'http://localhost:8884',
            //             /* 图片提供方式 */
            //             ways_of_supply: '后台上传',
            //             /* 图片提供入口 */
            //             ways_of_supply_link: 'http://localhost:8884',
            //             /* 图片来源 */
            //             source: 'K站 Konachan-CHS',
            //             /* 图片来源链接 */
            //             source_link: 'https://konachan.net/sample/b07496edaf042e99b90bb0f77fc1c3ef/Konachan.com%20-%20305360%20sample.jpg?0.26283345924835855'
            //         }
            //     }
            // },
            /* 消息弹窗 */
            message_alert_parameter: {
                duration: {
                    zero_ms: '0',
                    one_ms: '1000',
                    two_ms: '2000',
                    three_ms: '3000',
                    four_ms: '4000',
                    five_ms: '5000',
                    six_ms: '6000',
                    seven_ms: '7000',
                    eight_ms: '8000',
                    nine_ms: '9000',
                    ten_ms: '10000'
                },
                showClose: {
                    t: 'true',
                    f: 'false'
                },
                type: {
                    s: 'success',
                    w: 'warning',
                    i: 'info',
                    e: 'error'
                }
            },
        };
    },
    build: {
        assetsPublicPath: '/',
        assetsSubDirectory: 'static'
    },
    methods: {
        download : function (){
            var elemIF = document.createElement("iframe");
              elemIF.src = "./static/Image_resources/wallpaper/quadratic_element-wallpaper-00001.jpg";
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
  /* 隐藏滚动条 */
  /* ::-webkit-scrollbar {
    height: 0;
    width: 0 !important;
  } */
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