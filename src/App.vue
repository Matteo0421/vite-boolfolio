<script>
import axios from 'axios';
import { store } from './data/store';
import Card from './components/Card.vue'
import Header from './components/Header.vue'

  export default {
    components:{
      Card,
      Header
    },

  }
</script>

<template>
  <div>
    <Header/>
    <router-view></router-view>
   
  </div>
</template>



<style lang="scss" scoped>

</style>