<template>
  <div class="home" id="home">

     <Banner msg="Welcome to Your Vue.js App"/>
     
     <AddPost msg="Welcome to Your Vue.js App"/>
     <PostList msg="Welcome to Your Vue.js App" :posts="posts" />

  </div>
</template>

<script>
import axios from "axios";


// @ is an alias to /src
import Banner from '@/components/Banner.vue';
import AddPost from '@/views/AddPost.vue';
import PostList from '@/views/PostList.vue';

export default {
  name: 'Home',
  data() {
    return {
      posts: [],
      errors: []
    }
  },
  components: {
    Banner,
    AddPost,
    PostList
  },
  created(){
    axios.get(`https://jsonplaceholder.typicode.com/posts?_limit=5`)  /* This is the api key path */
    .then(response => {
      this.posts = response.data
    })
    .catch(e => {
      this.errors.push(e);
    })
  }
}
</script>
