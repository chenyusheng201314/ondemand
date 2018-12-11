<template>
  <div class="case-detail-all" @scroll.native="handleScroll($event)">
    <div class="case-detail">
      <img :src="bg" alt="" class="case-detail-banner" width="100%">
      <Site :data="address"></Site>
      <!--导航-->
      <div class="case-detail-nav" :class="{ position : position_type }" id="nav">
        <a
          v-for="(item,index) in case_info.detail"
          :key="index"
          :class="{choose : now_nav === index}"
          @click="tab_choose(index)"
          :href="'#tit' + index"
        >{{item.title}}</a>
      </div>
      <!--标题 简介-->
      <div class="case-detail-model">
        <p class="case-model-title">{{case_info.title}}</p>
        <div class="case-detail-introduce">{{case_info.introduce}}</div>
      </div>
      <!-- 主体内容-->
      <div class="case-detail-model">
        <ul class="case-detail-ul">
          <li v-for="(item,index) in case_info.detail" :key="index" :id="'tit' + index">
            <div class="title-fir">
              <p>● {{item.title}}</p>
            </div>
            <div class="case-detail-main" v-for="(it,ind) in item.con">
              <p class="main-tit">{{it.title}}</p>
              <p class="main-con">{{it.con}}</p>
            </div>
          </li>
        </ul>
      </div>
      <!--其它案列-->
      <div class="case-detail-model">
        <div class="title-fir">
          <p>● 其他案例</p>
        </div>
        <div class="other-case">
          <div class="swiper-container swiper-case">
            <div class="swiper-wrapper">
              <div class="swiper-slide" v-for="(item,index) in case_list" :key="index">
                <ul class="case-lists">
                  <li v-for="(it,ind) in item" :key="ind">
                    <a :href="'/case/detail?'+ it.id">
                      <img :src="it.pic" alt="">
                      <p class="case-tit">{{it.name}}</p>
                    </a>
                  </li>
                </ul>
              </div>
            </div>
            <!--分页器-->
            <div class="swiper-button-prev banner-prev">⟨</div><!--左箭头-->
            <div class="swiper-button-next banner-next">⟩</div><!--右箭头-->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

  import Swiper from 'swiper'
  import 'swiper/dist/css/swiper.min.css'
  import Site from '~/components/site'

  export default {
    name: "detail",
    components: {
      Site,
      Swiper
    },
    data() {
      return {
        bg: '/images/bg-case.jpg',
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '企业案例', link: '/case', next_show: false},
        ],
        now_nav: 0,
        position_type: false,
        case_info: {
          title: '某银行企业-敏捷培训评估体系建设',
          introduce: '该客户是中国最早参与国内外金融市场融资的商业银行，并以屡创中国现代金融史上多个第一而蜚声海内外。 伴随中国经济的快速发展，该银行在中国金融市场改革的大潮中逐渐成长壮大，目前，已成为国内资本实力最雄厚的商业银行之一，是一家快速增长并具有强大综合竞争力的全国性商业银行。 本次的服务对象为该银行的全国信用卡中心。',
          detail: [
            {
              title: '项目背景和需求',
              link: 'add1',
              con: [
                {
                  title: '外部环境',
                  con: '随着互联网金融的高速发展，公司面临的压力越来越大为取得更好的业绩，需对人员的综合能力有更多训练和提升',
                },
                {
                  title: '信用卡中心',
                  con: '计划未来独立上市，对近三年的业绩体量和质量提出了更高要求对人员综合能力提升有更大需求，要求人才培养更有效率、效果',
                },
                {
                  title: '培训中心',
                  con: '暂无法科学开发和运用评估工具，不能大范围评价课程项目，难全面掌控培训质量和效果培训评估体系尚不完善，培训效果的过程管理尚不够标准化，培训效果保障机制有缺失'
                },
                {
                  title: '项目需求',
                  con: '建立一套科学有效、系统规范的评估体系对人才发展项目和各项培训活动开展评估'
                },
                {
                  title: '项目目标',
                  con: '建立一套适合中信信用卡中心实际需求的评估体系\n' +
                  '通过集训和辅导使培训中心的学员了解柯氏四级评估的核心要素\n' +
                  '通过集训和辅导使培训中心的相关人员掌握评估工具的调整与应用的方法\n' +
                  '通过工作坊共创的方式建立评估手册(含管理与领导力、专业技能2个维度)'
                },
              ],
            },
            {
              title: '项目解决方案及成果展示',
              link: 'add2',
              con: [
                {
                  title: '',
                  con: '理论与实践相结合，做中学，培养一批企业的培训评估人才开发出适应当前需求的评估模型及工具，丰富其评估的理论及实践，形成有效的评估机制。统一企业培训评估语系，形成培训评估的文化氛围。完成企业培训评估体系建设，有效指导培训项目评估。',
                },
              ],
            },
            {
              title: '项目收益',
              link: 'add3',
              con: [
                {
                  title: '',
                  con: '理论与实践相结合，做中学，培养一批企业的培训评估人才开发出适应当前需求的评估模型及工具，丰富其评估的理论及实践，形成有效的评估机制。统一企业培训评估语系，形成培训评估的文化氛围。完成企业培训评估体系建设，有效指导培训项目评估。',
                },
              ],
            },
            {
              title: '项目参与人员',
              link: 'add4',
              con: [
                {
                  title: '',
                  con: '理论与实践相结合，做中学，培养一批企业的培训评估人才开发出适应当前需求的评估模型及工具，丰富其评估的理论及实践，形成有效的评估机制。统一企业培训评估语系，形成培训评估的文化氛围。完成企业培训评估体系建设，有效指导培训项目评估。',
                },
              ],
            },
            {
              title: '客户证言',
              link: 'add5',
              con: [
                {
                  title: '',
                  con: '该项目深度企业高层及培训管理者的好评\n' +
                  '随后该企业又采购了安迪曼咨询的课程体系规划项目和培训管理者能力提升项目',
                },
              ],
            },
          ]
        },
        case_list: [
          [
            {
              id: 1,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 2,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 3,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 4,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 5,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 6,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 7,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 8,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 9,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 10,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
          ],
          [
            {
              id: 1,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 2,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 3,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 4,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 5,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 6,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 7,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 8,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 9,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
            {
              id: 10,
              pic: '/images/index/case.png',
              name: '某银行企业-敏捷培训评估体系'
            },
          ],
        ],
        // 导航吸顶用
        nav_top: '',
        case_id: '',
        scroll_top: [],
      }
    },
    methods: {
      init() {
        const that = this;
        // 无ID 跳回到列表页
        let id = window.location.href.split('?')[1];
        if (!id) {
          that.$router.push({path: '/case'})
        } else {
          that.case_id = id;
        }
        // 案例
        new Swiper('.swiper-case', {
          autoplay: false,
          delay: 3000,
          loop: true,
          speed: 500,
          grabCursor: false,
          // 如果需要分页器
          pagination: {
            el: '.swiper-pagination-case',
            clickable: true
          },
          navigation: {
            nextEl: '.banner-next',
            prevEl: '.banner-prev'
          },
        });
      },
      // 锚点跳转获取到顶部高度
      get_all_top() {
        const that = this;
        that.scroll_top = [];
        that.case_info.detail.forEach((val, key) => {
          let top = document.getElementById('tit' + key).offsetTop;
          that.scroll_top.push(top);
        });
      },

      tab_choose(index) {
        this.now_nav = index;
      },
      handleScroll(event) {
        const that = this;
        let top = event.target.scrollingElement.scrollTop;
        // 滚到对应的区域 对应的标题加上效果
        if (top >= (this.nav_top - 10)) {
          that.position_type = true;
          that.get_all_top();
          for (let i = 0; i < that.scroll_top.length - 1; i++) {
            if (top < (that.scroll_top[i + 1] - 30)) {
              that.now_nav = i
              return false
            } else {
              that.now_nav = i + 1
            }
          }
        } else {
          that.position_type = false;
        }


      }
    },
    mounted() {
      this.init();
      window.addEventListener('scroll', this.handleScroll, true);
      setTimeout(() => {
        this.nav_top = document.getElementById('nav').offsetTop;
        console.log('nav-top', this.nav_top);

      }, 100);
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
