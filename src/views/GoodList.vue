<template>
  <div class="layout">
    <nav-header></nav-header>
    <nav-bread></nav-bread>
    <div class="layout-content">
      <div class="layout-content-main">Content</div>
    </div>
    <nav-footer></nav-footer>
  </div>
</template>

<script>
  import NavHeader from './../components/NavHeader.vue'
  import NavBread from './../components/NavBread.vue'
  import NavFooter from './../components/NavFooter.vue'

  export default {
    data() {
      return {}
    },
    components: {
      NavHeader,
      NavBread,
      NavFooter
    }
  }
</script>

<style scoped>
  .layout{
    border: 1px solid #d7dde4;
    background: #f5f7f9;
  }

  .layout-content{
    min-height: 200px;
    margin: 15px;
    overflow: hidden;
    background: #fff;
    border-radius: 4px;
  }
  .layout-content-main{
    padding: 10px;
  }

</style>

