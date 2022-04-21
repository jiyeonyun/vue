<template>
<NavBar/>
  <router-view :posts="posts">
  </router-view>
</template>



<script>
import post from './assets/post.js';
import NavBar from './components/NavBar.vue';
export default {
  name: 'App',
  data(){
    return{
      posts : post
    }
  },
  components: {
    NavBar,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
