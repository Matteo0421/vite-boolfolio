<template>
  <main class="flex-shrink-0">

    <!-- Header-->
    <header class="py-5">
      <div class="container px-5 pb-5">
        <div class="row gx-5 align-items-center">
          <div class="col-xxl-5">
            <!-- Header text content-->
            <div class="text-center text-xxl-start">
              <div class="badge bg-danger text-white mb-4">
                <div class="text-uppercase">Web Developer Full-Stack</div>
              </div>
              <h1 class="display-3 fw-bolder mb-5"><span class="">Ciao sono Matteo</span>
              </h1>
              <div class="d-grid gap-3 d-sm-flex justify-content-sm-center justify-content-xxl-start mb-3">
                <router-link :to="{name: 'about'}" class="btn btn-outline-dark btn-lg px-5 py-3 fs-6 fw-bolder" >About</router-link>
                <router-link :to="{name: 'projects'}" class="btn btn-outline-dark btn-lg px-5 py-3 fs-6 fw-bolder" >Progetti</router-link>
              </div>
            </div>
          </div>
          <div class="col-xxl-7">
            <!-- Header profile picture-->
            <div class="d-flex justify-content-center mt-5 mt-xxl-0">
              <div class="profile bg-danger">
                <img src="" alt="">
              </div>
            </div>
          </div>
        </div>
      </div>
    </header>
    <!-- About Section-->
    <section class="bg-light py-5">
      <div class="container px-5">
        <div class="row gx-5 justify-content-center">
          <div class="col-xxl-8">
            <div class="text-center my-5">
              <h2 class="display-5 fw-bolder"><span class=" d-inline">Chi sono?</span></h2>
              <p class="lead fw-light mb-4">
                Sono Matteo, ho 20 anni ed ho la passione per l'informatica e l'economia, questi sono alcuni dei miei progetti
              </p>
              <div class="d-flex justify-content-center fs-2 gap-4">
                <a class="" href="#!"><i class="text-danger bi-twitter"></i></a>
                <a class="" href="#!"><i class=" text-danger bi-linkedin"></i></a>
                <a class="" href="#!"><i class="text-danger bi-github"></i></a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style lang="scss" scoped></style>