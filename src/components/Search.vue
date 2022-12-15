<script>
import { store } from '../store';

export default {
    name: "Search",
    props :{
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="bar">
        <div class="bar">
            <input v-model="store.searchText" placeholder="Search..." type="text">
            <select name="selectStatus" id="selectStatus">
                <option value="any">Any</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>
            <button @click="$emit( 'search' )">Search</button>
            <button @click="$emit( 'reset' )">Reset</button>
        </div>

    </div>
</template>

<style lang="scss" scoped>
    .bar {
        display: flex;
        gap: 20px;
        
    }
</style>
