<template>
  <div class="layout">
    <nav-header></nav-header>
    <nav-bread></nav-bread>
    <div class="layout-content">
      <div class="layout-content-main">
        <Row :gutter="16">
          <Col span="6">
          <Menu active-name="1" >
            <MenuGroup title="PRICE" @on-select="priceChoose">
              <MenuItem name="0">All</MenuItem>
              <MenuItem v-for="(price, index) in priceFilter" :key="price.id" v-bind:name='index+1'>
                {{price.startPrice}} - {{price.endPrice}}
              </MenuItem>
            </MenuGroup>
          </Menu>
          </Col>
          <Col span="18">
          <Row>
            <div class="sort_info">
              <p>Sort by:
                <RadioGroup v-model="sort_choice" type="button" size="small" class="sort_btn">
                  <Radio label="default"></Radio>
                  <Radio label="price"></Radio>
                </RadioGroup>
              </p>
            </div>
          </Row>
          <Row :gutter="16">
            <Col span="6" v-for="item in goodList" :key="item.productId">
            <Card class="card_box">
              <img v-lazy="'/static/' + item.productImg" alt="">
              <h3>{{item.productName}}</h3>
              <p>${{item.productPrice}}</p>
              <Button type="default" long>Add to Cart</Button>
            </Card>
            </Col>
          </Row>
          </Col>
        </Row>
      </div>
    </div>
    <nav-footer></nav-footer>
  </div>
</template>

<script>
  import NavHeader from './../components/NavHeader.vue'
  import NavBread from './../components/NavBread.vue'
  import NavFooter from './../components/NavFooter.vue'
  import axios from 'axios'

  export default {
    data() {
      return {
        goodList: [],
        sort_choice: 'default',
        priceFilter: [
          {
            id: 1,
            startPrice: '0',
            endPrice: '500'
          },
          {
            id: 2,
            startPrice: '500',
            endPrice: '1000'
          },
          {
            id: 3,
            startPrice: '1000',
            endPrice: '2000'
          }
        ]
      }
    },
    components: {
      NavHeader,
      NavBread,
      NavFooter
    },
    mounted: function () {
      this.getGoodsList();
    },
    methods: {
      getGoodsList() {
        axios.get('/goods').then((result) => {
          var res = result.data;
          this.goodList = res.result;
        })
      },
      priceChoose(priceId) {

      }
    }
  }
</script>

<style scoped>
  .layout {
    border: 1px solid #d7dde4;
    background: #f5f7f9;
  }

  .layout-content {
    min-height: 200px;
    margin: 15px;
    overflow: hidden;
    background: #fff;
    border-radius: 4px;
  }

  .layout-content-main {
    padding: 10px;
  }

  .card_box {
    margin-bottom: 15px;
  }

  .card_box img {
    width: 100%;
    height: 100%;
  }

  .sort_info {
    height: 40px;
    line-height: 40px;
    border-bottom: 1px solid #e9eaec;
    margin-bottom: 15px;
  }

  .sort_info p {
    display: inline-block;
    float: right;
  }

  .sort_btn {
    display: inline-block;
    margin-left: 10px;
  }
</style>

