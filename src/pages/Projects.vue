<script>
import axios from 'axios';
import { store } from '@/data/store';
import Card from '@/components/Card.vue';
export default {
  components: {
    Card,
  },
  data() {
    return {

      projects: [],

    }
  },

  methods: {
    getApi() {
      axios.get(store.apiUrl)
        .then(result => {
          console.log(result.data);
          this.projects = result.data
        })
        .catch(error => {
          console.log(error.message);
        })

    }
  },

  mounted() {
    this.getApi();
  }

}
</script>

<template>
  <div>
    <section class="py-5">
      <div class="container px-5 mb-5">
        <div class="text-center mb-5">
          <h1 class="display-5 fw-bolder mb-0"><span class=" d-inline">Projects</span></h1>
        </div>
        <div class="row gx-5 justify-content-center">
          <div class="col-lg-11 col-xl-9 col-xxl-8">
            <!-- Project Card 1-->
            <Card v-for=" project in projects" :key="project.id" :title="project.title" :image="project.image"
              :description="project.description" />

          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<style lang="scss" scoped></style>