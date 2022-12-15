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
            <input placeholder="Search..." type="text">
            <button id="send">Search</button>
            <button id="reset">Reset</button>
        </div>
        <div class="bar">
            <select name="selectStatus" id="selectStatus">
                <option value="any">Any</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .bar {
        display: flex;
        gap: 20px;
        
    }
</style>
