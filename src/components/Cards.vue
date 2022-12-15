<script>
export default {
    name: "Cards",
    props :{
        immagine: String,
        nome: String,
        status: String,
    },
    data() {
        return {
            
        }
    }
}
</script>

<template>
    <div class="card">
        <img :src="immagine" :alt="nome">
        <h3>{{nome}}</h3>
        <h5>{{status}}</h5>
    </div>
</template>

<style scoped>
    .card {
        height: 300px;
        width: 200px;
        border-radius: 25px;
        background-color: black;
        padding: 10px;
        
    }
    img {
        width: 200px;
        height: auto;
        border-radius: 100px;
    }
    h3, h5 {
        color: white;
    }
</style>
