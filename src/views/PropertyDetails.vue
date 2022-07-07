<template>
    <div v-if="property" class="prop">
        <!-- <h1>This is property Details</h1> -->
        <!-- <p>The Job id is {{ $route.params.id}}</p> -->
           <div class="container">
             <h1>{{ property.title }}</h1>
            <h1>{{ property.area }}</h1>
            <img :src="property.image" />
           </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            // id: this.$route.params.id
        property: null
        }
    },
    mounted() {
    fetch("http://localhost:3000/properties/" + this.$route.params.id)
    .then (res  => res.json())
    .then (data => {
        this.property = data
        console.log(data)
        })
    }
}
</script>
<style>
    .container{
        border: 1px solid black;
        padding: 10px;
        margin-inline: 20%;
        
    }
    img{
        width: 300px;
        height: 300px;
    }
    /* .prop{
        height: 100vh;
        justify-content: center;
        align-items: center;
    } */
</style>