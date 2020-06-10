<template>
    <div class="post-list">
        <h4 class="pb-5">
            Add Post here
        </h4>
        <div class="card bg-inverse mb-4" v-for="post of posts" :key="post.id"> 
            <div class="card-body">
                <h3 class="card-title mb-3 mt-0"> <router-link :to="`/post-details/${post.id}`">{{post.title}}</router-link></h3>
                <p class="card-text">{{post.body}} </p>
            </div>
        </div>

        <div class="card bg-inverse mb-4" v-if="errors && errors.length"> 
            <div class="card-body">
                <p class="card-text" v-for="(errors, index) of errors" :key="index">{{error.message}}</p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'PostList',
  props: ["posts"]
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.card-body a {
    background: transparent;
}
</style>
