<template>
  <div class="con">
    <Head :now_nav="now_nav"></Head>
    <nuxt-child></nuxt-child>
    <Footer></Footer>
  </div>
</template>

<script>
  import Head from '~/components/head'
  import Footer from '~/components/footer'

  export default {
    name: "teacher",
    components: {
      Head,
      Footer
    },
    data() {
      return {
        now_nav: 3,
      }
    }
  }
</script>

<style scoped>

</style>
