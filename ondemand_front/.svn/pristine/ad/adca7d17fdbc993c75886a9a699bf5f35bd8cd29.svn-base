<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <ul class="tea-lists">
        <li class="tea-list" v-for="(item,index) in teacher_list" :key="index">
          <a :href="'/teacher/detail?' + item.id">
            <img :src="item.pic" alt="">
            <p class="tea-name">
              <label>{{item.name}}</label>
              <span>{{item.position}}</span>
            </p>
            <ul class="tea-tips">
              <li v-for="(it,ind) in item.tips" v-if="ind < 4">{{it}}</li>
            </ul>
          </a>
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
    name: "index",
    components: {
      Site
    },
    data() {
      return {
        bg: '/images/bg-tea.jpg',
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '讲师队伍', link: '/teacher', next_show: false},
        ],
        paging: {
          page: 1,
          size: 20,
          total: 100,
        },
        teacher_list: [
          {
            id: 1,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 2,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 3,
            name: '崔连斌',
            pic: '/images/index/tea1.png',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 4,
            name: '崔连斌',
            pic: '/images/index/tea1.png',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 1,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 2,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 3,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 4,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 1,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 2,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 3,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
          },
          {
            id: 4,
            pic: '/images/index/tea1.png',
            name: '崔连斌',
            position: '博士',
            tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师'],
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
          href: '/css/teacher.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
