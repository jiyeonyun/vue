<template>
    <div>
        <h5>{{posts[$route.params.id].title}}</h5>
        <p>{{posts[$route.params.id].content}}</p>
        <span>{{posts[$route.params.id].date}}</span>
        <router-view/>
    </div>
</template>

<script>
export default {
    name: "detail-page",
    props:{
        posts : Array,
    }
}
</script>

<style>

</style>