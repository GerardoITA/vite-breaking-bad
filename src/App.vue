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

      let filteredApiURL = store.apiURL;
      if (store.searchText !== ""){
        filteredApiURL += `?name=${store.searchText}`;
      }
      axios
        .get(filteredApiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
    },
    clearText() {
      store.searchText = "";
    }
  },
  mounted(){
    this.getCharacters();
  }
}
</script>

<template>
  <main>
    <Search @search="getCharacters" @reset="clearText"></Search>
    <CharacterList></CharacterList>
  </main>
</template>

<style lang="scss">
@use './style/general.scss'
</style>
