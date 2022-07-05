<template>
   <div class="card-display">
    <PropertyCard v-for="property in Properties" :key="property.id " :property="property"/>
    <!-- <div v-for="property in Properties" :key="property.id" class="card">
    <div class="cards">
        <img :src="property.image">
        <h2>{{ property.title }}</h2>
        <p>{{ property.area }}</p>
        <p>{{ property.bedroom }}</p>
        
    </div>
    </div> -->
    
   </div>
   
</template>
<script>
import PropertyCard from "../components/PropertyCard.vue"
export default {
    components: {PropertyCard},
    data() {
         return {
        Properties:[],
    }
    },
    mounted(){
        fetch("http://localhost:3000/Properties")
        .then((res) => res.json())
        .then((data) => (this.Properties =data))
        .catch(err => console.log(err.message))
        }
    }
   
</script>
<style>
.card{
    padding: 20px;
    box-shadow: 10px 10px 10px 10px lightgrey;
    border-radius: 10px;
}
.card h2{
    font-size: 1rem;
}
    .cards{
        width: 300px;
        height: fit-content;
        box-shadow: 10px 10px 10px 10px lightslategray;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 20px;

    }
    .cards:hover{
        box-shadow: 10px 10px 10px 10px lightslategray;
        transition: 0.5s all ease-in-out;
    }
    .card-display{
        display: flex;
    gap: 30px;
    justify-content: center;
    align-items: center;
    padding: 10px;
    flex-wrap: wrap;
    margin-top: 200px;
    background-image: url(./images/C:\Users\Admin\Vue\vue-navbar\images\aditya-chinchure-S1ToogvRvlU-unsplash.jpg);
    }
    img{
        position: relative;
    height: 200px;
    width: 200px;
    border-radius: 10px;
    }
    nav{
       position: fixed;
       top: 0;
       left: 0;
       width: 100%;
       background: lightslategray;
       z-index: 100;
    }
    #app{
        height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
   
    }
</style>