<template>
  <div>
    <div class="static-banner" :style="{backgroundImage: 'url(' + bg + ')', backgroundSize:'cover'}"></div>
    <div class="model-main">
      <Site :data="address"></Site>
      <ul class="person-ul">
        <li class="person-li">
          <div class="title-fir">
            <p>● 个人信息</p>
          </div>
          <div class="person-from">
            <div class="up-head">
              <img :src="info.pic_url" alt="">
              <p>上传头像</p>
              <el-upload
                class="up-pic"
                action="https://jsonplaceholder.typicode.com/posts/"
                :show-file-list="false"
                :on-success="handleAvatarSuccess"
                :before-upload="beforeAvatarUpload">
                <img v-if="imageUrl" :src="imageUrl" class="avatar">
                <i v-else class="el-icon-plus avatar-uploader-icon"></i>
              </el-upload>
            </div>
            <ul>
              <li>
                <label>昵称</label>
                <input type="text">
              </li>
            </ul>
          </div>
        </li>
      </ul>
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
        bg: '/images/bg-acc.jpg',
        address: [
          {name: '首页', link: '/', next_show: true},
          {name: '账户中心', link: '/person', next_show: false},
        ],
        info: {
          pic_url: '/images/person/head.png',
          pic_name: '',
          name: '',
          birthday: '',
          sex: '',
          mail: '',
          address: '',
          num: '',
          company_name: '',
          position: '',
          year: '',
          industry: '',
        },
      }
    },
    head: {
      link: [
        {
          href: '/css/person.css',
          type: 'text/css',
          rel: 'stylesheet',
        },
      ]
    }
  }
</script>

<style scoped>

</style>
