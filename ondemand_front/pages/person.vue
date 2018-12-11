<template>
  <div>
    <Head :now_nav="now_nav"></Head>
    <nuxt-child></nuxt-child>
    <Footer></Footer>
  </div>
</template>

<script>
  import Head from '~/components/head'
  import Footer from '~/components/footer'
  export default {
    name: "person",
    components: {
      Head,
      Footer
    },
    data() {
      return {
        now_nav: -1,
      }
    }
  }
</script>

<style scoped>

</style>
