<template>
  <div class="now-site">
    <span>当前位置:</span>
    <span v-for="(item,index) in data" :key="index">
      <a :href="item.link" :class="{add_now: !item.next_show}">{{item.name}}</a>
      <label v-if="item.next_show">></label>
    </span>
  </div>
</template>

<script>
  export default {
    name: "site",
    props: ['data'],
  }
</script>

<style scoped>

</style>
