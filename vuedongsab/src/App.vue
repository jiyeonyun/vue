<template>
<div v-if="modalOpen === true" class="black-bg">
  <div class="white-bg">
    <h4>상세페이지임</h4>
    <p>상세페이지 내용임</p>
    <button @click="modalOpen = false">모달 닫기</button>
  </div>  
</div>

  <div class="nav">
    <a v-for="(menu,i) in menus" :key="i">{{menu}}</a>
  </div>
  <div v-for='(product,i) in products' :key='i'>
    <img :src="product.image" class="room-img"/>
    <h4 @click="modalOpen = true">{{product.title}}</h4>
    <p>{{product.price}} 원</p>
    <p>{{product.content}}</p>
  </div>
</template>

<script>

import room from './post.js'

export default {
  name: 'App',
  data(){
    return{
      imgs : [require('./assets/room0.jpg'),require('./assets/room1.jpg'),require('./assets/room2.jpg')],
      modalOpen : false,
      products : room,
      menus : ['home' , 'about' , 'products'],
    }
  },
  //함수만드는 공간
  methods:{
    // increase(a){this.신고수[a]++} //this.써야 데이터 사용가능
  },
  components: {
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
.black-bg{
  width:100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width:100%; 
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.room-img{
  width: 30rem;
  margin-top: 2rem;
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
