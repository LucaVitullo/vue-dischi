<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent/>
  </div>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue'

import MainComponent from '@/components/MainComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
};
</script>

<style lang="scss">

@import '@/style/general';

body{
  background-color: #1e2d3b;
}


</style>
