<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <div class="online-tab">
        <span v-for="(item,index) in data" :key="index" :class="{m_r_130: index === 0}">
            <nuxt-link :to="item.link" :class="{choose:index === now_tab}">{{item.name}}</nuxt-link>
        </span>
      </div>
      <ul class="online-lists">
        <li v-for="(item,index) in course_lists" :key="index" @click="down_cover_type= true">
          <img :src="item.cover" alt="">
          <p class="online-list-tit">{{item.title}}</p>
          <p class="online-list-info">
            <span><img src="/images/online/time1.png" alt="">{{item.nums}}课时</span>
            <span><img src="/images/online/time2.png" alt="">{{item.times}}小时</span>
          </p>
        </li>
      </ul>
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

    <!--线上课程下载APP弹窗-->
    <el-dialog
      title=""
      :visible.sync="down_cover_type"
      width="465px">
      <img src="/images/ewm.png" alt="">
    </el-dialog>
  </div>

</template>

<script>
  import Site from '~/components/site'

  export default {
    name: "index",
    components: {
      Site
    },
    props: ['data'],
    data() {
      return {
        bg: '/images/bg-course.jpg',
        now_tab: 0,
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '课程列表', link: '/online-course', next_show: true},
          {name: '线上课程', link: 'javascript:;', next_show: false},
        ],
        course_lists: [
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
          {
            id: 1,
            title: '中国培训行业发展趋势解读',
            cover: '/images/online/cover.png',
            times: 1.6,
            nums: 15
          },
        ],
        paging: {
          page: 1,
          size: 20,
          total: 100,
        },
        down_cover_type: false,
      }
    },
    methods: {
      current_change(val) {
        console.log('当前页', val)
      }
    },
    mounted() {
      console.log(this.data);
    },
    head: {
      link: [
        {
          href: '/css/online.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
