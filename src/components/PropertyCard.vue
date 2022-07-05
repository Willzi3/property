<template>
     <div class="card">
        <img :src="property.image">
        <h2>{{ property.title }}</h2>
        <p>{{ property.area }}</p>
        <p>{{ property.bedroom }}</p>
        
    </div>
</template>
<script>
export default {
    props: ['property'],
}
</script>
<style>
    
</style>