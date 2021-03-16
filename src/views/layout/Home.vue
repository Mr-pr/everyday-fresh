<template>
  <div class="home">
    <left-menu :key="key"/>
    <div :class="{ 'main-app': true, 'menu-unfold': $store.state.collapsed }">
      <slider-header />
      <router-view/>
    </div>
  </div>
</template>

<script>

import LeftMenu from './components/menu.vue';

import SliderHeader from './components/header.vue';

export default {
  components: { LeftMenu, SliderHeader },

  data() {
    return {
      key: new Date().getTime(),
    };
  },
  watch: {
    $route() {
      this.key = new Date().getTime();
    },
  },
};
</script>
<style lang="less" >
@import url("~@/assets/css/home.less");
</style>
