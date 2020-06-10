<template>
  <div id="app">

    <Header msg="Welcome to Your Vue.js App"/>

    <div class="container">
      
      <router-view/>
    
    </div>


    <Footer msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>

import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'


export default {
  components: {
    Header,
    Footer
  }
}
</script>


<style>

body {
  background: #222831 !important;
  color: #fff !important;
}

.card {
  background: #1a1d24 !important;
  border-radius: 8px !important;
}

.card-body {
  background: #1a1d24;
}

.card-body a{
  background: #efbb35;
}


</style>
