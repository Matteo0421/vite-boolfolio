<script>
import axios from 'axios';
import { store } from './data/store';
import Card from './components/Card.vue'

  export default {
    components:{
      Card
    },

    data(){
      return{

        projects: [],

      }
    },

    methods:{
      getApi(){
        axios.get(store.apiUrl)
        .then(result =>{
          console.log(result.data);
          this.projects = result.data
        })
        .catch(error=>{
          console.log(error.message);
        })

      }
    },

    mounted(){
      this.getApi();
    }

  }
</script>

<template>
  <div>
    <h2> Lista Progetti</h2>
    <ul>
      <li v-for="project in projects" :key="project.id">
         {{ project.id }} - {{ project.title }}
      </li>
    </ul>
  </div>

  <div class="text-center  container  ">
    <div class="row row-cols-4  p-3">
      <Card v-for=" project in projects"
        :key="project.id"
        :title="project.title"
        :image="project.image"
        :description="project.description"
        />

    </div>
  </div>
</template>



<style lang="scss" scoped>

</style>