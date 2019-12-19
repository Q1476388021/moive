<template>
    <div id="content">
        <div style="border-bottom:1px dashed darkgrey;margin-bottom: 15px;">
        <h2>豆瓣电影排行榜</h2>
        <h4>豆瓣新片榜......</h4>
        </div>
        <el-row v-for="movie in movieList" type="flex" justify="center" :gutter="1" style="border-bottom: 1px dashed darkgrey;margin-top: 15px;" >
            <h2>
                {{movie.title}}
            </h2>
            <el-col :span="5" >
                <img src="../assets/1.jpg" style="width: 150px;height:230px;margin-bottom: 35px;">
            </el-col>
            <el-col :span="11" style="text-align: left">
                <div>
                    导演： {{movie.director}}
                </div>
                <div>
                    编剧：
                    <template v-for="(a,index) in movie.author">
                        <span style="color:#37a">{{a}}</span>
                        <template v-if="index!=movie.author.length-1">
                            /
                        </template>
                    </template>
                </div>
                <div>
                    主演：
                    <template v-for="(a,index) in movie.actors">
                        <span style="color:#37a">{{a}}</span>
                        <template v-if="index!=movie.actors.length-1">
                            /
                        </template>
                    </template>
                </div>
                <div>类型：{{movie.category}}</div>
                <div>
                    官方网站：
                    <a :href="movie.address" target="_blank">{{movie.address}}</a>
                </div>
                <div>
                    制片国家/地区：{{movie.country}}
                </div>
                <div>
                    语言：{{movie.lan}}
                </div>
                <div>
                    上映日期：{{movie.publishDate}}
                </div>
                <div>
                    片长：{{movie.timeLength}} 分钟
                </div>
                <div>
                    又名：{{movie.alias}}
                </div>
                <el-row>
                <el-rate span="4"
                        v-model="movie.value"
                        disabled
                        show-score
                        text-color="#ff9900"
                        score-template="{value}">
                </el-rate>
                    <el-col span="4">
                        <div style="font-size:12px;color:#37a;padding-left: 3px">
                            ({{movie.amount}}人评价)
                        </div>
                    </el-col>
                </el-row>
            </el-col>
        </el-row>
    </div>
</template>
<script>
    import ElProgress from "../../node_modules/element-ui/packages/progress/src/progress";
    export default {
        components: {ElProgress},
        created: function () {
            this.movie.title = this.$route.params.title;
        },
        data () {
            return {
                movieList:[

                    {
                        amount:48091,
                        value:4.8,
                        director: "托德·菲利普斯",
                        author: [
                            "托德·菲利普斯",
                            "斯科特·西尔弗",
                            "鲍勃·凯恩",
                            "比尔·芬格"],
                        actors: [
                            "杰昆·菲尼克斯",
                            "罗伯特·德尼罗",
                            "马克·马龙",
                            "莎姬·贝兹",
                            " 谢伊·惠格姆"
                        ],
                        category: "剧情 / 惊悚 / 犯罪",
                        address: "http://www.jokermovie.net",
                        country: "加拿大 / 美国",
                        lan: "英语",
                        publishDate: "2019-08-31",
                        timeLength: "122",
                        alias: "小丑起源电影：罗密欧 / Romeo / Joker Origin ",
                        title: "小丑",
                        describe: "电影《小丑》以同名DC漫画角色为基础，由华纳兄弟影业公司发行，计划于2019年10月4日上映。" +
                            "本片的故事将独立于DCEU之外，故事背景设置在20世纪80年代，讲述了一位生活陷入困境的脱口秀喜剧演员渐渐走向精神的崩溃，在哥谭市开始了疯狂的犯罪生涯，最终成为了蝙蝠侠的宿敌“小丑”的故事。" +
                            "本片由《宿醉》的导演托德菲利普斯执导，他与编剧斯科特西尔弗一起撰写了编剧。杰昆菲尼克斯本片中饰演主人公“小丑”，其他的主演包括罗伯特德尼罗、莎姬贝兹、马克马龙等。",

                    },
                    {
                        amount:47091,
                        value:4.7,
                        director: "托德·菲利普斯",
                        author: [
                            "托德·菲利普斯",
                            "斯科特·西尔弗",
                            "鲍勃·凯恩",
                            "比尔·芬格"],
                        actors: [
                            "杰昆·菲尼克斯",
                            "罗伯特·德尼罗",
                            "马克·马龙",
                            "莎姬·贝兹",
                            " 谢伊·惠格姆"
                        ],
                        category: "剧情 / 惊悚 / 犯罪",
                        address: "http://www.jokermovie.net",
                        country: "加拿大 / 美国",
                        lan: "英语",
                        publishDate: "2019-08-31",
                        timeLength: "122",
                        alias: "小丑起源电影：罗密欧 / Romeo / Joker Origin ",
                        title: "小丑",
                        describe: "电影《小丑》以同名DC漫画角色为基础，由华纳兄弟影业公司发行，计划于2019年10月4日上映。" +
                            "本片的故事将独立于DCEU之外，故事背景设置在20世纪80年代，讲述了一位生活陷入困境的脱口秀喜剧演员渐渐走向精神的崩溃，在哥谭市开始了疯狂的犯罪生涯，最终成为了蝙蝠侠的宿敌“小丑”的故事。" +
                            "本片由《宿醉》的导演托德菲利普斯执导，他与编剧斯科特西尔弗一起撰写了编剧。杰昆菲尼克斯本片中饰演主人公“小丑”，其他的主演包括罗伯特德尼罗、莎姬贝兹、马克马龙等。",

                    },
                    {
                        amount:45091,
                        value:4.6,
                        director: "托德·菲利普斯",
                        author: [
                            "托德·菲利普斯",
                            "斯科特·西尔弗",
                            "鲍勃·凯恩",
                            "比尔·芬格"],
                        actors: [
                            "杰昆·菲尼克斯",
                            "罗伯特·德尼罗",
                            "马克·马龙",
                            "莎姬·贝兹",
                            " 谢伊·惠格姆"
                        ],
                        category: "剧情 / 惊悚 / 犯罪",
                        address: "http://www.jokermovie.net",
                        country: "加拿大 / 美国",
                        lan: "英语",
                        publishDate: "2019-08-31",
                        timeLength: "122",
                        alias: "小丑起源电影：罗密欧 / Romeo / Joker Origin ",
                        title: "小丑",
                        describe: "电影《小丑》以同名DC漫画角色为基础，由华纳兄弟影业公司发行，计划于2019年10月4日上映。" +
                            "本片的故事将独立于DCEU之外，故事背景设置在20世纪80年代，讲述了一位生活陷入困境的脱口秀喜剧演员渐渐走向精神的崩溃，在哥谭市开始了疯狂的犯罪生涯，最终成为了蝙蝠侠的宿敌“小丑”的故事。" +
                            "本片由《宿醉》的导演托德菲利普斯执导，他与编剧斯科特西尔弗一起撰写了编剧。杰昆菲尼克斯本片中饰演主人公“小丑”，其他的主演包括罗伯特德尼罗、莎姬贝兹、马克马龙等。",

                    },
                    {
                        amount:42091,
                        value:4.5,
                        director: "托德·菲利普斯",
                        author: [
                            "托德·菲利普斯",
                            "斯科特·西尔弗",
                            "鲍勃·凯恩",
                            "比尔·芬格"],
                        actors: [
                            "杰昆·菲尼克斯",
                            "罗伯特·德尼罗",
                            "马克·马龙",
                            "莎姬·贝兹",
                            " 谢伊·惠格姆"
                        ],
                        category: "剧情 / 惊悚 / 犯罪",
                        address: "http://www.jokermovie.net",
                        country: "加拿大 / 美国",
                        lan: "英语",
                        publishDate: "2019-08-31",
                        timeLength: "122",
                        alias: "小丑起源电影：罗密欧 / Romeo / Joker Origin ",
                        title: "小丑",
                        describe: "电影《小丑》以同名DC漫画角色为基础，由华纳兄弟影业公司发行，计划于2019年10月4日上映。" +
                            "本片的故事将独立于DCEU之外，故事背景设置在20世纪80年代，讲述了一位生活陷入困境的脱口秀喜剧演员渐渐走向精神的崩溃，在哥谭市开始了疯狂的犯罪生涯，最终成为了蝙蝠侠的宿敌“小丑”的故事。" +
                            "本片由《宿醉》的导演托德菲利普斯执导，他与编剧斯科特西尔弗一起撰写了编剧。杰昆菲尼克斯本片中饰演主人公“小丑”，其他的主演包括罗伯特德尼罗、莎姬贝兹、马克马龙等。",
                    },
                ]
            }
        }
    }
</script>
}