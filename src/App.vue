<script>
import CharacterList from './components/CharacterList.vue'
import Search from './components/Search.vue'
import axios from 'axios';

import { store } from '../src/store';

export default {
  name: "App",
  components: {
    CharacterList,
    Search,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      axios
        .get(store.apiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
    }
  },
  mounted(){
    this.getCharacters();
  }
}
</script>

<template>
  <main>
    <Search></Search>
    <CharacterList></CharacterList>
  </main>
</template>

<style lang="scss">
@use './style/general.scss'
</style>
