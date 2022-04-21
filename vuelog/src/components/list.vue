<template>
    <div v-for="(post,a) in posts" :key="a">
        <h5 @click="$router.push(`/detail/${a}`)">{{post.title}}</h5>
        <p>{{post.date}}</p>
    </div>
</template>

<script>
export default {
    name: 'List-blog',
    props:{
        posts : Array,
    }
}
</script>

<style>

</style>