<template>
    <div id="post-details">
       <div class="card bg-inverse bg-dark mb-3"> 
            <div class="card-body">
                <h3 class="card-title mb-3 mt-0"> <div class="">{{post.id}} </div>  {{post.title}} </h3>
                <p class="card-text">{{post.body}} </p>
            </div>
        </div>

      <PostComments msg="Welcome to Your Vue.js App"/>
    </div>

</template>

<script>
  import axios from 'axios';
  import PostComments from '@/views/PostComments.vue';

export default {
  name: 'PostDetails',
  components: {
    PostComments
  },
  data() {
    return {
      id: this.$route.params.id,
      post: []
    };
  },
  created() {
    axios
      .get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)  /* This is the api key path */
      .then(response => {
        this.post = response.data;
      })
      .catch(e => {
        this.errors.push(e);
      })
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
