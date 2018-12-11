<template>
  <div class="con">
    <div class="ondemand-index">
      <!--banner轮播-->
      <div class="position-relative">
        <div class="swiper-container swiper-container-banner row">
          <div class="swiper-wrapper">
            <div class="swiper-slide swiper-slide-banner" v-for="(item,index) in banners" :key="index">
              <a target="_blank" style="display: block;width: 100%;height: 100%;" :href="item.url">
                <!--<img class="swiper-img-banner" :src="item" alt="没有？" />-->
                <div class="swiper-img-banner-bg" :style="'background-image: url('+ item.src +')'"></div>
              </a>
            </div>
          </div>
          <!-- 如果需要分页器 -->
          <div class="swiper-pagination swiper-pagination-banner"></div>
          <div class="swiper-button-prev banner-prev">⟨</div><!--左箭头-->
          <div class="swiper-button-next banner-next">⟩</div><!--右箭头-->
        </div>
      </div>

      <!--公开课-->
      <div class="index-model">
        <p class="model-title">公开课</p>
        <p class="model-en-tit">Offline Courses</p>
        <span class="model-more">
          <img src="/images/index/more.png" alt="">
        </span>
        <ul class="index-course">
          <li v-for="(item,index) in course" :key="index">
            <img :src="item.url" alt="">
            <p class="li-tit">{{item.tit}}</p>
            <p class="li-con">{{item.con}}</p>
          </li>
        </ul>
      </div>

      <!--线上课程-->
      <div class="index-model">
        <p class="model-title">线上课程</p>
        <p class="model-en-tit">Online Courses</p>
        <span class="model-more">
          <nuxt-link to="/online-course">
            <img src="/images/index/more.png" alt="">
          </nuxt-link>
        </span>
        <div class="online-course">
          <div class="swiper-container swiper-online-course">
            <div class="swiper-wrapper">
              <div class="swiper-slide" v-for="(item,index) in online_class" :key="index">
                <div class="pic-card" v-for="(it,ind) in item" :key="ind" :class="{m_r_53: ind !== 3}"
                     @click="down_cover_type= true">
                  <!-- 这里的a标签 方便以后跳转  目前只是弹窗-->
                  <!--<a href="javascript:;">-->
                  <img :src="it.url" alt="">
                  <p class="pic-card-tit">{{it.title}}</p>
                  <p class="pic-card-teacher">{{it.teacher}} | {{it.post}}</p>
                  <p class="pic-card-time">
                    <span><img src="/images/index/time1.png" alt="">{{it.nums}}课时</span>
                    <span><img src="/images/index/time2.png" alt="">{{it.times}}小时</span>
                    <span></span>
                  </p>
                  <!--</a>-->
                </div>
              </div>
            </div>
            <!--分页器-->
            <div class="swiper-pagination swiper-pagination-course"></div>
          </div>
        </div>
      </div>

      <!--公司新闻，行业资讯-->
      <div class="index-news">
        <div class="company-news">
          <span class="model-more">
            <nuxt-link to="/news/dynamic">
              <img src="/images/index/more.png" alt="">
            </nuxt-link>
        </span>
          <h3>公司动态</h3>
          <p class="news-en-tit">Company Dynamics<span></span></p>
          <ul class="company-news-list">
            <li v-for="(item,index) in company_news" :key="index">
              <!--跳转-->
              <a href="javascript:;">
                <div class="news-pic">
                  <img :src="item.pic" alt="">
                </div>
                <div class="news-main">
                  <p class="news-main-title">{{item.title}}</p>
                  <p class="news-main-con">{{item.dec}}</p>
                  <p class="news-main-date">{{item.date}}</p>
                </div>
              </a>
            </li>
          </ul>
        </div>
        <div class="industry-news">
          <span class="model-more">
            <nuxt-link to="/news">
              <img src="/images/index/more.png" alt="">
            </nuxt-link>
          </span>
          <h3>行业资讯</h3>
          <p class="news-en-tit">Industry Consultation<span></span></p>
          <ul class="industry-list">
            <li v-for="(item,index) in industry_news" :key="index">
              <!--跳转-->
              <a href="javascript:;">
                <div class="news-pic">
                  <img :src="item.pic" alt="">
                </div>
                <div class="news-main">
                  <p class="main-title">{{item.title}}</p>
                  <p class="main-date">{{item.date}}</p>
                </div>
              </a>
            </li>
          </ul>
        </div>

      </div>

      <!--导师队伍-->
      <div class="index-model">
        <p class="model-title">讲师队伍</p>
        <p class="model-en-tit">Lecturer Team</p>
        <span class="model-more">
          <a href="/teacher">
            <img src="/images/index/more.png" alt="">
          </a>
        </span>
        <div class="index-teacher">
          <div class="swiper-container swiper-teacher">
            <div class="swiper-wrapper">
              <div class="swiper-slide" v-for="(item,index) in teacher_lists" :key="index">
                <ul class="teacher-list">
                  <li v-for="(it,ind) in item" :key="ind">
                    <a :href="'/teacher/detail?'+ it.id">
                      <img :src="it.pic" alt="">
                      <p class="teacher-name">
                        <label>{{it.name}}</label>
                        <span>{{it.position}}</span>
                      </p>
                      <ul class="teacher-tips">
                        <li v-for="(i,key) in it.tips" :key="key" v-if="key < 4">{{i}}</li>
                      </ul>
                    </a>
                  </li>
                </ul>
              </div>
            </div>
            <!--分页器-->
            <div class="swiper-pagination swiper-pagination-teacher"></div>
          </div>
        </div>
      </div>

      <!--证书查询-->
      <div class="index-model">
        <p class="model-title">证书查询</p>
        <p class="model-en-tit">Certificate Inquiry</p>
        <div class="index-certificate">
          <div class="certificate-logo">
            <img src="/images/index/university-logo.png" alt="">
          </div>
          <div class="enter-btn">进入安迪曼大学进行查询</div>

        </div>
      </div>

      <!--名师博客-->
      <div class="index-model">
        <p class="model-title">名师博客</p>
        <p class="model-en-tit">Tutor's Blog</p>
        <span class="model-more">
          <img src="/images/index/more.png" alt="">
        </span>
        <ul class="blog-lists">
          <li v-for="(item,index) in blog_list" :key="index" v-if="index< 5">
            <p class="blog-li-date">{{item.date}}</p>
            <p class="blog-li-main">
              <a href="javascript:;">{{item.title}}</a>
              <label>{{item.teacher}}</label>
            </p>
          </li>
        </ul>
        <div class="blog-line"></div>
        <ul class="blog-lists">
          <li v-for="(item,index) in blog_list" :key="index" v-if="index< 10 && index > 4">
            <p class="blog-li-date">{{item.date}}</p>
            <p class="blog-li-main">
              <a href="javascript:;">{{item.title}}</a>
              <label>{{item.teacher}}</label>
            </p>
          </li>
        </ul>
      </div>

      <!--服务案例-->
      <div class="index-model">
        <p class="model-title">服务客户</p>
        <p class="model-en-tit">Customer Service</p>
        <span class="model-more">
          <img src="/images/index/more.png" alt="">
        </span>
        <div class="index-case">
          <div class="swiper-container swiper-case">
            <div class="swiper-wrapper">
              <div class="swiper-slide" v-for="(item,index) in case_list" :key="index">
                <ul class="case-lists">
                  <li v-for="(it,ind) in item" :key="ind">
                    <a href="javascript:;">
                      <img :src="it.pic" alt="">
                      <p class="case-tit">{{it.name}}</p>
                    </a>
                  </li>
                </ul>
              </div>
            </div>
            <!--分页器-->
            <div class="swiper-pagination swiper-pagination-case"></div>
          </div>
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
  </div>
</template>

<script>
  import Swiper from 'swiper'
  import 'swiper/dist/css/swiper.min.css';

  export default {
    name: "index",
    components: {
      Swiper
    },
    data() {
      return {
        // banner
        banners: [
          {
            src: '/images/index/banner01.jpg',
            url: ''
          }, {
            src: '/images/index/banner02.jpg',
            url: ''
          }, {
            src: '/images/index/banner03.jpg',
            url: ''
          }, {
            src: '/images/index/banner04.jpg',
            url: ''
          }
        ],
        //公开课
        course: [
          {
            url: '/images/index/class1.png',
            tit: '组织经验萃取',
            con: '每一家优秀企业都会在某一特定领域积累下优秀的经验，但这些经验大多每一家优秀企业都会在某一特定领域积累下优秀的经验，但这些经验大多'
          },
          {url: '/images/index/class2.png', tit: '完美授课技巧', con: '什么样的授课才叫完美？授课技巧=呈现技巧吗？'},
          {url: '/images/index/class3.png', tit: '敏捷课程设计与开发', con: '如果您对课程开发有如下需求，这门课程可能会适合您：以团队模式封'},
          {url: '/images/index/class4.png', tit: '柯氏四级培训效果评估', con: '您所在的企业大学/培训部门如何对 培训效果 进行评估？没有？只'},
          {url: '/images/index/class5.png', tit: '基于岗位序列的课程体系', con: '或许对于很多培训专业人士而言，下面的问题早已屡见不鲜：业务部门...'},
          {url: '/images/index/class6.png', tit: '业务结果导向的在岗带教', con: '我们的企业有没有遇到这些问题：不知道如何复制传承企业优秀的经验？...'},
        ],
        //在线课程
        online_class: [
          [{
            url: '/images/index/course.png',
            id: 1,
            title: '如何快速有效呈现培训价值',
            teacher: '胡丽',
            post: '博士',
            times: '1.8',
            nums: '18'
          },
            {
              url: '/images/index/course.png',
              id: 2,
              title: '培训需求分析',
              teacher: '崔连斌',
              post: '博士',
              times: '1.6',
              nums: '12'
            },
            {
              url: '/images/index/course.png',
              id: 3,
              title: '培训管理者专业成长路径',
              teacher: '崔连斌',
              post: '博士',
              times: '12',
              nums: '18'
            },
            {
              url: '/images/index/course.png',
              id: 4,
              title: '基于行为改变的课程设计啊啊啊啊',
              teacher: '胡丽',
              post: '博士',
              times: '1.8',
              nums: '18'
            },],

          [{
            url: '/images/index/course.png',
            id: 1,
            title: '如何快速有效呈现培训价值',
            teacher: '胡丽',
            post: '博士',
            times: '1.8',
            nums: '18'
          },
            {
              url: '/images/index/course.png',
              id: 2,
              title: '培训需求分析',
              teacher: '崔连斌',
              post: '博士',
              times: '1.6',
              nums: '12'
            },
            {
              url: '/images/index/course.png',
              id: 3,
              title: '培训管理者专业成长路径',
              teacher: '崔连斌',
              post: '博士',
              times: '12',
              nums: '18'
            },
            {
              url: '/images/index/course.png',
              id: 4,
              title: '基于行为改变的课程设计啊啊啊啊',
              teacher: '胡丽',
              post: '博士',
              times: '1.8',
              nums: '18'
            },],

        ],
        // 在线课程弹窗显示
        down_cover_type: false,
        // 公司新闻
        company_news: [
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '内训师精准赋能，南京沙龙活动报道',
            dec: '由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的',
            date: '2018-11-12',
          },
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '内训师精准赋能，南京沙龙活动报道',
            dec: '由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的',
            date: '2018-11-12',
          },
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '内训师精准赋能，南京沙龙活动报道',
            dec: '由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的由安迪曼咨询主办的《内训师精准赋能》沙龙活动走进南京询主办的',
            date: '2018-11-12',
          },

        ],
        // 行业资讯
        industry_news: [
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '培训是否等于“学习”，建立学习型组织的要素',
            date: '2018-11-21'
          },
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '培训是否等于“学习”，建立学习型组织的要素',
            date: '2018-11-21'
          },
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '培训是否等于“学习”，建立学习型组织的要素',
            date: '2018-11-21'
          },
          {
            id: 1,
            pic: '/images/index/company-news.png',
            title: '培训是否等于“学习”，建立学习型组织的要素',
            date: '2018-11-21'
          },
        ],
        teacher_lists: [
          [
            {
              id: 1,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 2,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 3,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 4,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 5,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 6,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 7,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 8,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
          ],
          [
            {
              id: 9,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 10,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 11,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 12,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 13,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
            {
              id: 14,
              pic: '/images/index/tea1.png',
              name: '崔连斌',
              position: '博士',
              tips: ['安迪曼首席CTO', 'ATD认证顾问', '柯氏四级认证讲师', 'DACUM导引师']
            },
          ],
        ],
        blog_list: [
          {
            title: '如何设计一个学习项目1？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？6（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          },
          {
            title: '如何设计一个学习项目？（下篇）',
            id: 1,
            date: '2018-11-22',
            teacher: '饶强',
          }
        ],
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
        ]
      }
    },
    methods: {
      init() {
        // banner
        new Swiper('.swiper-container-banner', {
          autoplay: true,
          delay: 3000,
          loop: true,
          speed: 500,
          grabCursor: false,
          // 如果需要分页器
          pagination: {
            el: '.swiper-pagination-banner',
            clickable: true
          },
          navigation: {
            nextEl: '.banner-next',
            prevEl: '.banner-prev'
          },
        });
        // 线上课程
        new Swiper('.swiper-online-course', {
          autoplay: false,
          delay: 3000,
          loop: true,
          speed: 500,
          grabCursor: false,
          // 如果需要分页器
          pagination: {
            el: '.swiper-pagination-course',
            clickable: true
          },
          // navigation: {
          //   nextEl: '.banner-next',
          //   prevEl: '.banner-prev'
          // },
        });
        // 老师
        new Swiper('.swiper-teacher', {
          autoplay: false,
          delay: 3000,
          loop: true,
          speed: 500,
          grabCursor: false,
          // 如果需要分页器
          pagination: {
            el: '.swiper-pagination-teacher',
            clickable: true
          },
          // navigation: {
          //   nextEl: '.banner-next',
          //   prevEl: '.banner-prev'
          // },
        });
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
          // navigation: {
          //   nextEl: '.banner-next',
          //   prevEl: '.banner-prev'
          // },
        });
      }
    },
    mounted() {
      this.init();
    },
    head: {
      link: [
        {
          href: '/css/index.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
