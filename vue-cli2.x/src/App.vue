<template>
  <div id="app">
    <mt-header title="固定在顶部"></mt-header>
    <router-view></router-view>
    <mt-tabbar v-model="selected">
      <mt-tab-item id="home">
        <img @click="changeHash" slot="icon" src="./assets/img/1.png">
        首页
      </mt-tab-item>
      <mt-tab-item id="member">
        <img @click="changeHash" slot="icon" src="./assets/img/2.png">
        会员
      </mt-tab-item>
      <mt-tab-item id="shopcart">
        <img @click="changeHash" slot="icon" src="./assets/img/3.png">
        购物车
      </mt-tab-item>
      <mt-tab-item id="search">
        <img @click="changeHash" slot="icon" src="./assets/img/4.png">
        查找
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>
export default {
  data () {
    return {
      selected: ''
    }
  },
  // watch: {
  //   selected (newV, oldV) {//监听的selected值在
  //     console.log(this)
  //     console.log(this.$router)
  //     this.$router.push({
  //       name: newV
  //     })
  //   }
  // },
  methods: {
    changeHash () {
      this.$nextTick(function () {
        console.log(this.selected)
        this.$router.push({
          name: this.selected
        })
      })
    }
  }
}
</script>

<style scoped>
  .mint-tabbar {
    position: fixed;
    bottom: 0px;
  }
</style>
