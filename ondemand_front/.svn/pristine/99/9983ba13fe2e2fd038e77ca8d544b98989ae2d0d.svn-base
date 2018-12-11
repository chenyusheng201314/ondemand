<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main tea-detail-main">
      <Site :data="address"></Site>
      <div class="title-fir">
        <p>● 讲师介绍</p>
      </div>
      <div class="tea-detail-info">
        <div class="tea-info-pic">
          <img src="/images/index/tea1.png" alt="">
        </div>
        <div class="tea-info-con">
          <p class="tea-con-name">
            <label>{{tea_info.name}}</label>
            <span>{{tea_info.position}}</span>
          </p>
          <p class="tea-introduce">
            {{tea_info.introduce}}
          </p>
          <div class="tea-bg">
            <div class="tea-bg-left pad-r-5">
              <h3>背景</h3>
              <p v-for="(item,index) in tea_info.bg" :key="index">{{index + 1}}. {{item}}</p>
            </div>
            <div class="tea-bg-left pad-l-5">
              <h3>专长</h3>
              <p v-for="(item,index) in tea_info.speciality" :key="index">{{index + 1}}. {{item}}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="title-fir m_t_60">
        <p>● 讲师详情</p>
      </div>
      <div class="tea-detail-detail">
        <h3>服务过的客户：</h3>
        <p>{{tea_info.client}}</p>
      </div>
      <div class="tea-detail-detail">
        <h3>专题研究：</h3>
        <p v-for="(item,index) in tea_info.research">{{index + 1}}. {{item}}</p>
      </div>
      <div class="tea-detail-detail">
        <h3>出版书籍：</h3>
        <p v-for="(item,index) in tea_info.book">{{index + 1}}. {{item}}</p>
      </div>
      <div class="tea-detail-detail">
        <h3>专业文章：</h3>
        <p v-for="(item,index) in tea_info.article">{{index + 1}}. {{item}}</p>
      </div>
    </div>
    <div class="model-main tea-detail-main tea-detail-main2">
      <span class="to-more">
        <nuxt-link to="/blog">
          <img src="/images/index/more.png" alt="">
        </nuxt-link>
      </span>
      <div class="title-fir">
        <p>● 他/她的博客</p>
      </div>
      <ul class="tea-detail-blog">
        <li v-for="(item,index) in tea_info.blog" :key="index">
          <a :href="'/blog/detail?' + item.id">{{item.name}}</a>
        </li>
      </ul>
    </div>
    <div class="model-main tea-detail-main tea-detail-main2">
      <span class="to-more">
         <img src="/images/index/more.png" alt="">
      </span>
      <div class="title-fir">
        <p>● 他/她的公开课</p>
      </div>
      <ul class="tea-open-list">
        <li v-for="(item,index) in tea_info.course" :key="index" v-show="index< 4">
          <img :src="item.cover" alt="">
          <p>{{item.name}}</p>
        </li>
      </ul>
    </div>
    <div class="model-main tea-detail-main tea-detail-main2">
      <span class="to-more">
        <nuxt-link to="/case">
          <img src="/images/index/more.png" alt="">
        </nuxt-link>
      </span>
      <div class="tea-detail-tit">
        <p>● 服务案例</p>
      </div>
      <ul class="tea-open-list">
        <li v-for="(item,index) in tea_info.tea_case" :key="index" v-if="index< 4">
          <a :href="'/case/detail?' + item.id">
            <img :src="item.cover" alt="">
            <p>{{item.name}}</p>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Site from '~/components/site'

  export default {
    name: "detail",
    components: {
      Site
    },
    data() {
      return {
        tea_id: '',
        bg: '/images/bg-tea.jpg',
        address: [],
        tea_info: {
          name: '崔连斌',
          position: '博士',
          introduce: '从2012年至今，每年主导完成中国培训行业研究，已完成中国培训管理者能力模型、中国企业人才发展等7份行业研究报告。此外，参与多本人力资源开发专业书籍的翻译出版：《ASTD培训经理指南》、《柯氏评估的过去和现在》、《培训审判》、《结构化在岗培训》、《ISPI绩效改进指南》等。曾任美国伊利诺伊州助理护士任职资格考试中心研究员，国内某知名咨询公司总经理。美国柯氏评估公司顾问，柯氏四级评估TM官方认证授权的中文讲师(目前仅有两位)。',
          bg: [
            '安迪曼咨询总裁',
            '美国南伊利诺伊大学人力资源开发博士',
            '伊利诺伊州助理护士资格认证中心博士后',
            '美国柯氏评估公司顾问/认证讲师',
            '安迪曼咨询公司资深顾问/讲师'
          ],
          speciality: [
            '柯氏四级培训效果评估',
            '培训课程设计与开发',
            '绩效改进技术',
            '课程体系/学习地图开发'
          ],
          client: '企业/政府机构服务经验包括美国伊利诺伊州政府、俄亥俄州教育局、伊利诺伊州卫生局、Cooper B-Line公司， Bosch(美国)、Old National Bank、 AT&T、TCL集团、强生医疗、广联达、李宁、德赛西威、南航、国航、工行、新奥集团、灵山集团、中广核、上海国资委、正大集团、正泰电器、天虹股份、腾讯、北大汇丰、中车集团、雅培、五星电器、华东空管、赛诺菲、中国移动、中国电信、国家电网等。',
          research: [
            '中国企业课程设计与开发行业研究报告2013--培训专业人士对专业课程设计与开发方法的应用实践，胡丽、崔连斌博士;美国安迪曼咨询公司、《培训》杂志联合。',
            '中国企业培训效果评估行业研究报告2013，胡丽博士、崔连斌博士;美国安迪曼咨询公司。',
            '中国企业培训培训管理者专业发展研究报告2013，胡丽博士、崔连斌博士;美国安迪曼咨询公司。',
            '中国企业随需应变的嵌入式学习行业研究报告2013，胡丽博士、崔连斌博士;美国安迪曼咨询公司。',
            '中国企业课程设计与开发行业研究报告2012--培训专业人士对专业课程设计与开发方法的应用实践(2012)，胡丽博士、崔连斌博士;美国安迪曼咨询公司、《培训》杂志联合进行。',
            '2015-2016年中国企业培训行业研究报告，胡丽博士、崔连斌博士;美国安迪曼咨询公司、《培训》杂志联合发布。'],
          book: [
            '《绩效改进技术--课程设计与培训实施》，崔连斌、胡丽等译，江苏人民出版社。',
            '《绩效改进技术--绩效改进方案的选择与实施》，崔连斌、胡丽等译，江苏人民出版社。',
            '《绩效改进技术--测量与评估》，崔连斌、胡丽等译，江苏人民出版社。',
            '《结构化在岗培训》崔连斌、胡丽等译，江苏人民出版社。',
            '《培训审判》(2011)，崔连斌、胡丽译，江苏人民出版社。',
            '《柯氏评估的过去与现在》(2011)，崔连斌、胡丽译，江苏人名出版社。',
            '《ASTD培训经理指南》(2010)，顾立民、李家强、崔连斌、胡丽、陈致中译，江苏人民出版社。'],
          article: [
            '从培训管理者到绩效改进顾问(2013)，胡丽博士、崔连斌博士，《培训》杂志2013年第4期。',
            '从ASTD全球大会看中美培训行业的差别(2012)，崔连斌博士，《培训》杂志2012年第8期。',
            '崔连斌：龙年断章(2012)，崔连斌博士，《培训》杂志2012年12月刊。',
            '柯氏四级的正见(2012)，胡丽博士、崔连斌博士，《培训》杂志2012年8月刊。',
            '10分钟掌握绩效改进：使用RAPID绩效改进模型快速提升员工与组织绩效(2012)，胡丽博士、崔连斌博士，《培训》杂志2013年2-3月合刊。',
            '迎接社会化学习(The New Wave of Social Learning)(2011)，崔连斌博士、胡丽博士，《培训》杂志2011年8月刊。',
            '全新的柯氏四级评估：量化培训预期，，柯克帕特里克著，崔连斌、胡丽译，《培训杂志》2010年11月刊',
            '全新的柯氏三级评估: 行为改变，柯克帕特里克著，崔连斌、胡丽译，《培训杂志》2010年10月刊',
            '全新的柯氏二级评估: 学员信心与承诺的重要性，柯克帕特里克著，崔连斌、胡丽译，《培训杂志》2010年9月刊',
            '全新的柯氏一级评估：反应量表(2010)，柯克帕特里克著，崔连斌、胡丽译，《培训杂志》2010年8月刊。',
            '博士论文：随需应变的嵌入式学习在美国企业中的应用研究(2010)。'],
          blog: [
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
            {id: 1, name: '懂得这个原理才能好好做培训'},
          ],
          course: [
            {
              id: 1,
              name: '基于岗位序列的课程体系设计',
              cover: '/images/index/course.png'
            },
            {
              id: 2,
              name: '基于岗位序列的课程体系设计',
              cover: '/images/index/course.png'
            },
            {
              id: 3,
              name: '基于岗位序列的课程体系设计',
              cover: '/images/index/course.png'
            },
            {
              id: 4,
              name: '基于岗位序列的课程体系设计',
              cover: '/images/index/course.png'
            },
          ],
          tea_case: [
            {
              id: 1,
              name: '某鞋服企业-内训师培养项目案例',
              cover: '/images/index/case.png'
            },
            {
              id: 2,
              name: '某鞋服企业-内训师培养项目案例',
              cover: '/images/index/case.png'
            },
            {
              id: 3,
              name: '某鞋服企业-内训师培养项目案例',
              cover: '/images/index/case.png'
            },
            {
              id: 4,
              name: '某鞋服企业-内训师培养项目案例',
              cover: '/images/index/case.png'
            },
            {
              id: 5,
              name: '某鞋服企业-内训师培养项目案例',
              cover: '/images/index/case.png'
            },
          ]
        },
      }
    },
    methods: {
      get_tea_info() {
        const that = this;
        // 获取到老师信息之后赋值给数组
        console.log('获取老师信息');
        that.address = [
          {name: '首页', link: '/', next_show: true},
          {name: '讲师队伍', link: '/teacher', next_show: true},
          {name: '崔连斌', link: 'javascript:;', next_show: false},
        ]

      },
      init() {
        const that = this;
        let url = window.location.href.split('?')[1];
        if (!url) {
          that.$router.push({path: '/teacher'})
        } else {
          that.tea_id = url;
          that.get_tea_info();
        }
      },
    },
    mounted() {
      this.init();
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
