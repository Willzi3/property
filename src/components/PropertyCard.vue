<template>
    <router-link :to="{name: 'PropertyDetails', params: {id: property.id}}">
        <div class="card">
            <img :src="property.image">
            <h2>{{ property.title }}</h2>
            <p>{{ property.area }}</p>
            <p>{{ property.bedroom }}</p>
        </div>
    </router-link>
</template>
<script>
export default {
    props: ['property'],
}
</script>
<style>
    a{
        text-decoration: none;
        color: rgb(71, 185, 71);
    }
</style>