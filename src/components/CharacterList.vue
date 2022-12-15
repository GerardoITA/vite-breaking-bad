<script>
import { store } from '../store.js';
import Cards from './Cards.vue'


export default {
    name: "CharacterList",
    components: {
        Cards
    },
    data() {
        return {
            store,
        }
    },
}
console.log(store.characterList.length)
</script>

<template>
    <h1>Assolutamente breaking bad api giuro</h1>
    <div v-for="card in store.characterList">
        <Cards
        :immagine="card.image"
        :nome="card.name"
        :status="card.status"></Cards>
    </div>
   
</template>

<style scoped>
    h1 {
        color: black;
    }
</style>
