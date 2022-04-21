<template>
    <div>
        <h5>{{posts.title}}</h5>
        <p>{{posts.date}}</p>
    </div>
</template>

<script>
export default {
    name: 'List-blog',
    props:{
        posts : Object,
    }
}
</script>

<style>

</style>