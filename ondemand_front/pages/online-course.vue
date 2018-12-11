<template>
  <div class="con">
    <Head :now_nav="now_nav"></Head>
    <nuxt-child :data="child"></nuxt-child>
    <Footer></Footer>
  </div>
</template>

<script>
  import Head from '~/components/head'
  import Footer from '~/components/footer'


  export default {
    name: "online-course",
    components: {
      Head,
      Footer,
    },
    data() {
      return {
        now_nav: -1,
        child: [
          {
            name: '线上课程',
            link:'/online-course',
          },
          {
            name: '项目视频',
            link:'/online-course/project',
          },
        ]
      }
    }
  }
</script>

<style scoped>

</style>
