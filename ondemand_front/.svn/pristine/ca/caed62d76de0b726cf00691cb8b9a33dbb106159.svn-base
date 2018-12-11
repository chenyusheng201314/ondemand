<template>
  <div class="con">
    <Head :now_nav="now_nav"></Head>
    <nuxt-child :tab="tab"></nuxt-child>
    <Footer></Footer>
  </div>
</template>

<script>
  import Head from '~/components/head'
  import Footer from '~/components/footer'

  export default {
    name: "news",
    components: {
      Head,
      Footer
    },
    data() {
      return {
        now_nav: 1,
        tab: [
          {
            name: '行业资讯',
            link:'/news'
          },
          {
            name: '最新动态',
            link:'/news/dynamic'
          },

        ]
      }
    }
  }
</script>

<style scoped>

</style>
