<template>
    <div v-for="(post,a) in posts" :key="a">
        <span>{{post.number + 1}}.</span>
        <h5>{{post.title}}</h5>
        <p>{{post.content}}</p>
        <span>{{post.date}}</span>
    </div>
</template>

<script>
export default {
    name: "detail-page",
    props:{
        posts : Object,
    }
}
</script>

<style>

</style>