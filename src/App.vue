<template>
  <div id="app">
    <v-header></v-header>
    <div class="tab">
     <div class="tab-item">商品</div>
     <div class="tab-item">评论</div>
     <div class="tab-item">商家</div>
    </div>
    <div class="content">
      I am content
    </div>
  </div>
</template>

<script>
import header from './components/header/header.vue';
export default{
  components: {
    'v-header': header
  }
};
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #app
    font-size: 56px
    background-color: red
</style>
