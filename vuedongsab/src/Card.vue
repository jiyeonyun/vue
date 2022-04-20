<template>
    <div>
        <img :src="product.image" class="room-img"/>
        <h4 @click="$emit('openModals')">{{product.title}}</h4>
        <p>{{product.price}} 원</p>
    </div>
</template>

<script>
export default {
    name : 'Card-Component',
    props:{
        product : Object,
    },
}
    
</script>

<style>
.room-img{
  width: 30rem;
  margin-top: 2rem;
}
</style>