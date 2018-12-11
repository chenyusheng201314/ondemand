<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <div class="blog-type">
        <span class="blog-type-left">文章分类：</span>
        <p class="blog-type-right">
          <span v-for="(item,index) in article_type" :key="index" :class="{choose: index === now_type}"
                @click="choose_type(index)">{{item}}</span>
        </p>
      </div>
      <div class="blog-sec-tit">
        <p>{{type_name}}</p>
      </div>
      <table class="article-list">
        <tr>
          <th>文章标题</th>
          <th>文章作者</th>
          <th>发布时间</th>
          <th>人气</th>
        </tr>
        <tr v-for="(item,index) in article_list" :key="index">
          <td width="520" class="article-tit"><a :href="'/blog/detail?' + item.id">{{item.name}}</a></td>
          <td width="290">{{item.teacher}}</td>
          <td width="196">{{item.date}}</td>
          <td width="111">{{item.hot}}</td>
        </tr>
      </table>
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
        bg: '/images/bg-blog.jpg',
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '名师博客', link: '/blog', next_show: false},
        ],
        // 当前分类
        now_type: 0,
        type_name: '全部',
        article_type: [
          '全部',
          '内训师培养',
          '培训管理者',
          '培训评估',
          '内训师培养',
        ],
        paging: {
          page: 1,
          size: 20,
          total: 100,
        },
        article_list: [
          {
            id: 1,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 2,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 3,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 4,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 5,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 1,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 2,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 3,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 4,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 5,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 1,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 2,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 3,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 4,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 5,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 1,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 2,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 3,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 4,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
          {
            id: 5,
            name: '如何设计一个学习项目？（下篇）',
            teacher: '饶强',
            date: '2018-11-12',
            hot: '10'
          },
        ]
      }
    },
    methods: {
      // 分类切换
      choose_type(index) {
        this.now_type = index;
      },
      current_change(val) {
        console.log('当前页', val)
      }
    },
    watch: {
      now_type() {
        this.type_name = this.article_type[this.now_type];
      }
    },
    head: {
      link: [
        {
          href: '/css/blog.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
