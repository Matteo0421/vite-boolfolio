<script>
import axios from 'axios';
import { store } from '@/data/store';
import Card from '@/components/Card.vue';
import Loader from '@/components/Loader.vue'

export default {
  components: {
    Card,
    Loader // Aggiungi il componente Loader
  },
  data() {
    return {
      projects: [],
      currentPage: 1,
      lastPage: 1,
      isLoading: false
    }
  },
  methods: {
    getApi(page = 1) {
      this.isLoading = true;
      axios.get(`${store.apiUrl}?page=${page}`)
        .then(result => {
          console.log(result.data);
          this.projects = result.data;
          this.currentPage = result.data.current_page;
          this.lastPage = result.data.last_page;
        })
        .catch(error => {
          console.log(error.message);
        })
        .finally(() => {
          this.isLoading = false;
        });
    },
    nextPage() {
      if (!this.isLoading && this.currentPage < this.lastPage) {
        this.getApi(this.currentPage + 1);
      }
    },
    prevPage() {
      if (!this.isLoading && this.currentPage > 1) {
        this.getApi(this.currentPage - 1);
      }
    },
    goToPage(page) {
      if (!this.isLoading) {
        this.getApi(page);
      }
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
          <h1 class="display-5 fw-bolder mb-0"><span class="d-inline">Projects</span></h1>
          <!-- Loader -->
          <Loader v-if="isLoading" />
        </div>
        <div v-if="!isLoading" class="row gx-5 justify-content-center">
          <div class="col-lg-11 col-xl-9 col-xxl-8">
            <Card v-for="project in projects.data" :project="project" :key="project.id" :title="project.title"
              :image="project.image" :description="project.description" />
          </div>
        </div>
        <nav v-if="!isLoading" aria-label="Page navigation">
          <ul class="pagination justify-content-center">
            <li class="page-item" :class="{ disabled: currentPage === 1 }">
              <a class="page-link text-danger bg-transparent" href="#" @click.prevent="prevPage">Previous</a>
            </li>
            <li v-for="page in lastPage" :key="page" class="page-item" :class="{ active: currentPage === page }">
              <a class="page-link text-danger bg-transparent" href="#" @click.prevent="goToPage(page)">{{ page }}</a>
            </li>
            <li class="page-item" :class="{ disabled: currentPage === lastPage }">
              <a class="page-link text-danger bg-transparent" href="#" @click.prevent="nextPage">Next</a>
            </li>
          </ul>
        </nav>

      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped></style>