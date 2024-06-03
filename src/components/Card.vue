<script>
export default {
  props: {

    title: String,
    description: String,
    image: String

  }

}
</script>


<template>
  <div class="card overflow-hidden shadow rounded-4 border-0 mb-5">
    <div class="card-body p-0">
      <div class="d-flex align-items-center">
        <div class="p-5">
          <h2 class="fw-bolder">{{title}}</h2>
          <p>
            {{ description }}
          </p>
        </div>
        <img :src="image" class="card-img-top rounded-circle hover-effect" :alt="title">
      </div>
    </div>
  </div>
</template>




<style lang="scss" scoped></style>
