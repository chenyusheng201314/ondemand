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
      <ul class="project-lists">
        <li v-for="(item,index) in project_list" :key="index" @click="down_cover_type=true">
          <div class="project-list-cover">
            <img :src="item.cover" alt="">
          </div>
          <div class="project-list-con">
            <p class="list-con-tit">{{item.tit}}</p>
            <p class="list-con-con">{{item.doc}}</p>
          </div>
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
    name: "project",
    components: {
      Site
    },
    props: ['data'],
    data() {
      return {
        bg: '/images/bg-course.jpg',
        now_tab: 1,
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '课程列表', link: '/online-course', next_show: true},
          {name: '项目视频', link: 'javascript:;', next_show: false},
        ],
        project_list: [
          {
            id: 1,
            cover: '/images/online/cover.png',
            tit: 'TDF线上微课',
            doc: '   安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力。'
          },
          {
            id: 1,
            cover: '/images/online/cover.png',
            tit: 'TDF线上微课',
            doc: '   安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力。'
          },
          {
            id: 1,
            cover: '/images/online/cover.png',
            tit: 'TDF线上微课',
            doc: '   安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力安迪曼在2015年-2016年与《培训》杂志合作的行业研究报告中，对标全球权威的ATD培训管理者能力模型，结合中国实际调研数据，发布了适合中国培训管理者的能力模型。TDF培养项目基于培训管理者胜任力标准和安迪曼方法论开发而成。基于TDF培养项目我们还开发了《TDF线上微课》的培训课程，让用户体验到混合式学习的魅力。'
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
