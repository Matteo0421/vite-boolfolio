<script>
import Contacts from '@/pages/Contacts.vue';

  export default {
    
  }
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-white py-3">
                <div class="container px-5">
                    <router-link :to="{name: 'home'}" class="nav-link" ><span class="fw-bolder ">Matteo Carola</span></router-link>
                    
                    <div class="collapse navbar-collapse" id="navbarSupportedContent">
                        <ul class="navbar-nav ms-auto mb-2 mb-lg-0 small fw-bolder">
                            <li class="nav-item"><router-link :to="{name: 'home'}" class="nav-link" >Home</router-link></li>
                            <li class="nav-item"><router-link :to="{name: 'projects'}" class="nav-link" >Progetti</router-link></li>
                            <li class="nav-item"><router-link :to="{name: 'contacts'}" class="nav-link" >Contacts</router-link></li>
                            <li class="nav-item"><router-link :to="{name: 'about'}" class="nav-link" >About</router-link></li>
                          
                        </ul>
                    </div>
                </div>
            </nav>
</template>


<style lang="scss" scoped>

</style>