<template>
  <Modal @modalClose='modalOpen = false' :modalOpen="modalOpen" :products="products" :clickedNum ="clickedNum"/>
  <div class="nav">
    <a v-for="(menu,i) in menus" :key="i">{{menu}}</a>
  </div>
  <Discount/>
  <Card @openModals="cliked(i)" v-for="(product,i) in products" :key="i"
        :product="products[i]"/>
  
</template>

<script>

import room from './post.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){
    return{
      modalOpen : false,
      products : room,
      menus : ['home' , 'about' , 'products'],
      clickedNum : 0,
    }
  },
  //함수만드는 공간
  methods:{
    // increase(a){this.신고수[a]++} //this.써야 데이터 사용가능
    cliked(i){
      this.modalOpen = true,
      this.clickedNum = i
    }
  },
  components: {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>
body{
  margin:0;
}
div{
  box-sizing: border-box;
}
h4{
  cursor: pointer;
}
button{
  cursor: pointer;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
