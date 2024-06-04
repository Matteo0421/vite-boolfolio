<script>
import axios from 'axios';
import { store } from './data/store';
import Card from './components/Card.vue'
import Header from './components/Header.vue'
import Head from './components/Head.vue'

  export default {
    components:{
      Card,
      Header,
      Head
    },

  }
</script>

<template>
  <div>
    <Head/>
    <Header/>
    <router-view></router-view>
   
  </div>
</template>



<style lang="scss" scoped>

</style>