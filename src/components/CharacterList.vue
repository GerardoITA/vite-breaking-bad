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
    <div v-for="card in store.characterList">
        <Cards></Cards>
    </div>
   
</template>

<style scoped>
</style>
