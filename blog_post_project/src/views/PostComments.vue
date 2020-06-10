<template>
    <div id="Post-comments">
        <div class="card mb-3" v-for="comment in comments" :key="comment.id">
          <div class="row no-gutters">
            <div class="col-md-2 p-3">
              <img class="card-img-top" :src="BrandLogo" alt="">
            </div>
            <div class="col-md-10">
              <div class="card-body">
                <h4 class="card-title">{{comment.name}} </h4>
                <p class="card-text">{{comment.body}} </p>
                <p>
                  <small class="text-muted">{{comment.email}}</small>
                </p> 
              </div>
            </div>
          </div>
        </div>
     
    </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'PostComments',
    data() {
      return {
        BrandLogo: "/img/logo.82b9c7a5.png",
        id: this.$route.params.id,
        comments: []
      };
    },
    created() {
      axios
      .get(`https://jsonplaceholder.typicode.com/comments?postsid=${this.id}`)  /* This is the api key path */
      .then(response => {
        this.comments = response.data;
      })
      .catch(errors => {
        this.errors.push(errors);
      });
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
