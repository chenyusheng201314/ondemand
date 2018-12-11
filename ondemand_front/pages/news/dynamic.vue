<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <div class="news-tab">
        <span v-for="(item,index) in tab" :key="index" :class="{m_r_130: index === 0}">
            <nuxt-link :to="item.link" :class="{choose:index === now_tab}">{{item.name}}</nuxt-link>
        </span>
      </div>
      <ul class="news-list">
        <li v-for="(item,index) in news_list" :key="index">
          <nuxt-link :to="'/news/detail?2-'+ item.id">
            <div class="news-list-cover">
              <img :src="item.pic" alt="">
            </div>
            <div class="news-list-main">
              <p class="list-main-tit">{{item.title}}</p>
              <p class="list-main-con">{{item.con}}</p>
              <p class="list-main-date">{{item.date}}</p>
            </div>
          </nuxt-link>
        </li>
      </ul>
      <!-- 分页-->
      <div class="page">
        <el-pagination
          background
          :page-size="paging.size"
          :current-page.sync="paging.page"
          layout="prev, pager, next"
          prev-text="上一页"
          next-text="下一页"
          @current-change="current_change"
          :total="paging.total">
        </el-pagination>
      </div>
    </div>
  </div>
</template>

<script>
  import Site from '~/components/site'

  export default {
    name: "dynamic",
    props: ['tab'],
    components: {
      Site
    },
    data() {
      return {
        bg: '/images/bg-news.jpg',
        now_tab: 1,
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '资讯动态', link: '/news', next_show: true},
          {name: '最新动态', link: 'javascript:;', next_show: false},
        ],
        paging: {
          page: 1,
          size: 20,
          total: 100,
        },
        news_list: [
          {
            id: 1,
            title: '内训师精准赋能，南京沙sss龙活动报道',
            con: '2018年11月13日，由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京，与来自碧桂园、圣和药业、苏宁易购、正大天晴等各行各业的30多名培训管理者共同度过了一段有价值、有意义的时光。',
            date: '2018-11-19',
            pic: '/images/online/cover.png'
          },
          {
            id: 2,
            title: '内训师精准赋能，南京沙sss龙活动报道',
            con: '2018年11月13日，由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京，与来自碧桂园、圣和药业、苏宁易购、正大天晴等各行各业的30多名培训管理者共同度过了一段有价值、有意义的时光。',
            date: '2018-11-19',
            pic: '/images/online/cover.png'
          },
          {
            id: 3,
            title: '内训师精准赋能，南京沙龙ss活动报道',
            con: '2018年11月13日，由安迪曼sss咨询主办的《内训师精准赋能》沙龙活动走进南京，与来自碧桂园、圣和药业、苏宁易购、正大天晴等各行各业的30多名培训管理者共同度过了一段有价值、有意义的时光。',
            date: '2018-11-19',
            pic: '/images/online/cover.png'
          },
          {
            id: 4,
            title: '内训师精准赋能，南京沙sss龙活动报道',
            con: '2018年11月13日，由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京，与来自碧桂园、圣和药业、苏宁易购、正大天晴等各行各业的30多名培训管理者共同度过了一段有价值、有意义的时光。',
            date: '2018-11-19',
            pic: '/images/online/cover.png'
          },
          {
            id: 5,
            title: '内训师精准赋能，南京沙sss龙活动报道',
            con: '2018年11月13日，由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京，与来自碧桂园、圣和药业、苏宁易购、正大天晴等各行各业的30多名培训管理者共同度过了一段有价值、有意义的时光。',
            date: '2018-11-19',
            pic: '/images/online/cover.png'
          },
        ]
      }
    },
    methods: {
      current_change(val) {
        console.log('当前页', val)
      }
    },
    head: {
      link: [
        {
          href: '/css/news.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
