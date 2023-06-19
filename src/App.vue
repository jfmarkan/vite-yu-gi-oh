<template>
      <AppHeader />
      <AppMain />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import {store} from './store.js';

export default {
  name: 'App',
  data(){
    return {
      store
    }
  },
  components:{
    AppHeader,
    AppMain,
  }
}

</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";

</style>
