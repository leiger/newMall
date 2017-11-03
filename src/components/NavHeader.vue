<template>
  <div>
    <Menu mode="horizontal" theme="dark" active-name="1">
      <div class="layout-logo">newMall</div>
      <div class="layout-nav">
        <MenuItem name="1">
          <Icon type="ios-navigate"></Icon>
          Item 1
        </MenuItem>
        <MenuItem name="2">
          <Icon type="ios-keypad"></Icon>
          Item 2
        </MenuItem>
        <MenuItem name="3">
          <Icon type="ios-analytics"></Icon>
          Item 3
        </MenuItem>
        <MenuItem name="4">
          <Icon type="ios-paper"></Icon>
          Item 4
        </MenuItem>
      </div>
      <div class="layout-ceiling">
        <div class="layout-ceiling-main">
          <a href="#">Login</a> |
          <a href="#">Log Out</a> |
        </div>
      </div>
    </Menu>
  </div>
</template>

<script>
  export default {
    data() {
      return {}
    }
  }
</script>

<style scoped>
  .layout-logo {
    width: 150px;
    color: #fff;
    float: left;
    text-align: center;
    font-weight: 600;
    font-size: 20px;
  }

  .layout-nav {
    width: 420px;
    margin: 0 auto;
  }

  .layout-ceiling-main {
    float: right;
    margin-right: 15px;
  }

  .layout-ceiling-main a {
    color: #9ba7b5;
  }
</style>


