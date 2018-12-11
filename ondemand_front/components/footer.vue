<template>
  <div class="con">
    <div class="footer">
      <div class="container">
        <div class="container-top">
          <div class="container-top-left">
            <img src="/images/footer/home_qrcode_peixunjianghur_.png" alt="">
            <img src="/images/footer/home_qrcode_andimandaxue_.png" alt="">
          </div>
          <div class="container-top-right">
            <div class="container-top-right-mian">
              <div class="mian-detail">
                <p>关于我们</p>
                <ul>
                  <li v-for="(item,index) in about" :key="index">
                    <nuxt-link :to="item.link">{{item.name}}</nuxt-link>
                  </li>
                </ul>
              </div>
              <div class="mian-detail">
                <p>培训江湖</p>
                <ul>
                  <li v-for="(item,index) in jianghu" :key="index">
                    <nuxt-link :to="item.link">{{item.name}}</nuxt-link>
                  </li>
                </ul>
              </div>
              <div class="mian-detail">
                <p>培训江湖</p>
                <ul>
                  <li v-for="(item,index) in help" :key="index">
                    <nuxt-link :to="item.link">{{item.name}}</nuxt-link>
                  </li>
                </ul>
              </div>
            </div>
            <div class="container-top-contact">
              <img src="/images/footer/tel.png" alt="">
            </div>
          </div>
        </div>
        <div class="container-bottom">
          <p class="container-bottom-address">
            <span v-for="(item,index) in address" :key="index" @mousemove="address_change(index)">{{item.name}}</span>
          </p>
          <p class="detail-address">{{detail_address}}</p>
          <p class="detail-address add2">唯一指定法务律师事务所：广东摩金律师事务所</p>
          <p class="footer-blogroll">
            <span>友情链接：</span>
            <nuxt-link v-for="(item,index) in blogroll" :to="item.link">{{item.name}}</nuxt-link>
          </p>
        </div>
      </div>
    </div>
    <div class="footer-copyright">
      <p>安迪曼教育咨询无锡有限公司 版权所有 <span>苏ICP备18019875号-1 苏ICP备18019875号-2</span> Copyright 2015-2018,OnDemand Consulting, All
        Rights Reserved.</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "footer1",
    data() {
      return {
        about: [
          {name: '安迪曼简介', link: ''},
          {name: '免责声明', link: ''},
          {name: '联系方式', link: ''},
          {name: '商务合作', link: ''},
        ],
        jianghu: [
          {name: '原创作家', link: ''},
          {name: '培训人社区', link: ''},
          {name: '培训人招聘', link: ''},
        ],
        help: [
          {name: '会员权益', link: ''},
          {name: '常见问题', link: ''},
        ],
        address: [
          {name: '北京', add: '安迪曼(北京公司) | 地址：北京市海淀区中关村西区善缘街1号立方庭大厦1-707室'},
          {name: '上海', add: '安迪曼(上海公司) | 地址：上海市普陀区曹杨路450号绿地和创大厦902室'},
          {name: '广东', add: '安迪曼(广州公司) | 地址：广东省广州市天河区华强路3号富力盈力大厦南塔1111室'},
          {name: '深圳', add: '安迪曼(深圳公司) | 地址：深圳市南山区科苑路6号科技园工业大厦502室'},
          {name: '济南', add: '安迪曼(济南公司) | 地址：山东省济南市历下区千佛山路5号华天大厦301室'},
          {name: '无锡', add: '安迪曼(无锡公司) | 地址：无锡市滨湖区绣溪路53号旭天科技园26号安迪曼大厦'},
        ],
        detail_address: '',
        // 友情链接
        blogroll: [
          {name: '塔伦特咨询', link: ''},
          {name: '塔伦特咨询', link: ''},
          {name: '塔伦特咨询', link: ''},
          {name: '塔伦特咨询', link: ''},
        ]
      }
    },
    methods: {
      address_change(index) {
        this.detail_address = this.address[index].add;
      }
    },
    mounted() {
      this.detail_address = this.address[0].add;
    },
    head: {
      link: [
        {
          href: '/css/footer.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
