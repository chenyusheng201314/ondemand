<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <div class="case-all">
        <div class="case-title">
          <p>● 餐饮/食品/快消品</p>
        </div>
        <ul class="case-list">
          <li v-for="(item,index) in case_list" :key="index">
            <a :href="'/case/detail?' + item.id">
              <img :src="item.cover" alt="">
              <p>{{item.title}}</p>
            </a>
          </li>
        </ul>
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
        bg: '/images/bg-case.jpg',
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '企业案例', link: '/case', next_show: false},
        ],
        case_list: [
          {
            id: 1,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 2,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 3,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 4,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 5,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 1,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 2,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 3,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 4,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
          {
            id: 5,
            cover: '/images/index/case.png',
            title: '某银行企业-敏捷培训评估体系建设'
          },
        ]
      }
    },
    methods:{

    },
    head: {
      link: [
        {
          href: '/css/case.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }

  }
</script>

<style scoped>

</style>
