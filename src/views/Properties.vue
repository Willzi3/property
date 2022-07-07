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
    background: white;
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
    .card:hover{
        box-shadow: 10px 10px 10px 10px #42b983;
        transition: 0.5s all ease-in-out;
    }
    .card-display{
        display: flex;
    gap: 30px;
    justify-content: center;
    align-items: center;
    padding: 10px;
    flex-wrap: wrap;
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
       background: #42b983;
       z-index: 100;
    }
    nav a.router-link-exact-active {
    color: white;
}
    #app{
            margin-top: 100px;
    }
    
</style>