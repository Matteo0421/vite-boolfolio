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
  <div class="col ">
    <div class="card border-0" style="width: 18rem;">
      <img :src="image" class="card-img-top rounded-circle hover-effect" :alt="title">
      <div class="card-body">
      <h5 class="card-title">{{ title }}</h5> 
      <p class="card-text">{{ description }}</p>
  </div>
    </div>
  </div>
</template>



<style lang="scss" scoped>
  .card{
    background-color: transparent;
  }img{
    width: 90%;
    margin: auto;
  }.hover-effect {
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  &:hover{
    transform: translateY(-5px); 
    box-shadow: 0 6px 8px rgba(0, 0, 0, 0.5);
  }
}
</style>

