<template>
    <div v-if="modalOpen === true" class="black-bg">
        <div class="white-bg">
        <h4>{{products[clickedNum].title}}</h4>
        <img :src="products[clickedNum].image" class="room-img">
        <p>{{products[clickedNum].content}}</p>
        <p>{{products[clickedNum].price}}원</p>
        <button @click="$emit('modalClose')">닫기</button>
    </div>  
</div>
</template>

<script>
export default {
    name: 'Modal-window',
    props:{
        products : Object,
        modalOpen : Boolean,
        clickedNum : Number,

    }
}
</script>

<style>
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
.room-img{
  width: 30rem;
  margin-top: 2rem;
  }
</style>