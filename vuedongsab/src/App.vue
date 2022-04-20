<template>
  <div class="nav">
    <a v-for="menu in menus" :key="menu">{{menu}}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">
  <div v-for="product in products" :key="product">
    <h4>{{product}}</h4>
    <p>80만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus : ['home' , 'about' , 'products'],
    }
  },
  components: {
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
  margin-top: 60px;
}
.nav{
  background: darkslateblue;
  padding:  15px;
  border-radius: 5px;
}
.nav a{
  color:  whitesmoke;
  padding: 10px;
}
</style>
