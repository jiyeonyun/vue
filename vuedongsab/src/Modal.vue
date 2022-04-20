<template>
    <div v-if="modalOpen === true" class="black-bg">
        <div class="white-bg">
        <h4>{{products[clickedNum].title}}</h4>
        <img :src="products[clickedNum].image" class="room-img">
        <p>{{products[clickedNum].content}}</p>
        <input v-model.number="month" type="number">개월
        <p>{{month}}개월 : {{products[clickedNum].price*month}}원</p>
        <button @click="$emit('modalClose')">닫기</button>
    </div>  
</div>
</template>

<script>
export default {
    name: 'Modal-window',
    data(){
        return{
            month : 1,
        }
    },
    watch:{
        month(a){
            if(typeof a ==='string'){
                alert('문자 입력하지마셈');
                this.month = 1;
            }
        }
    },
    props:{
        products : Object,
        modalOpen : Boolean,
        clickedNum : Number,
    },
    beforeUpdate(){
        if(this.month == 2){
            alert('2개월은 안돼요')
        }
        if(this.month == -2){
            this.month = 3;
        }
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