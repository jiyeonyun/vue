<template>
  <transition name="fade">
    <Modal @modalClose='modalOpen = false' :modalOpen="modalOpen" :products="products" :clickedNum ="clickedNum"/>
  </transition>
  
  <div class="nav">
    <a v-for="(menu,i) in menus" :key="i">{{menu}}</a>
  </div>
  <Discount v-if="showDiscount === true" :discountPercent="discountPercent" />
  <button @click="priceSort()">가격순 정렬</button>
  <button @click="priceSortRe()">가격역순 정렬</button>
  <button @click="sortGanada()">가나다 정렬</button>
  <button @click="sortBack()">되돌리기</button>
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
      originProducts : room,
      modalOpen : false,
      products : [...room],
      menus : ['home' , 'about' , 'products'],
      clickedNum : 0,
      showDiscount : true,
      discountPercent : 30,
    }
  },
  //함수만드는 공간
  methods:{
    // increase(a){this.신고수[a]++} //this.써야 데이터 사용가능
    cliked(i){
      this.modalOpen = true,
      this.clickedNum = i
    },
    priceSort(){
      this.products.sort(
        function(a,b){
          return a.price-b.price
        }
      );
    },
    priceSortRe(){
      this.products.sort(
            function(a,b){
              return b.price-a.price
            }
          );
    },
    sortBack(){
      this.products = [...this.originProducts];
    },
    sortGanada(){
      this.products.sort(
        function(a,b){
          if(a.title<b.title)return -1;
          if(a.title>b.title) return 1;
          return 0
        }
      );
    },
  },
  mounted(){
      setInterval(() => {
          if(this.discountPercent>0){
            this.discountPercent --;
          }
      }, 1000);
  },
  components: {
    Discount,
    Modal,
    Card,
  }
}
</script>

<style>
.fade-enter-from{
  transform: translateY(-1000px);
}
.fade-enter-active{
  transition: all 1s;
}
.fade-enter-to{
  transform: translateY(0px);
}
.fade-leave-from{
  transform: translateY(0px);
}
.fade-leave-active{
  transition: all 1s;
}
.fade-leave-to{
  transform: translateY(-1000px);
}

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
