<template>
  <div id="home">
    <nav id="nav" class="navbar navbar-expand-lg navbar-bark bg-light mb-5">
      <div class="container">
        <router-link to="/" class="navbar-brand"> <img v-bind:src="BrandLogo" alt="Vue logo"></router-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown"
          aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item active">
              <router-link to="/" class="nav-link">{{HomeLink}}</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/about" class="nav-link">{{AboutLink}}</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
  export default {
    name: 'Header',
    data() {
      return {
        BrandLogo: "/img/logo.82b9c7a5.png",
        HomeLink: 'Home',
        AboutLink: 'About Us',
      }
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .navbar {
    background: #1a1d24 !important;
  }

  .navbar-nav a {
    color: #fff;
  }

  .navbar-nav a.router-link-exact-active {
    color: #42b983
  }
</style>