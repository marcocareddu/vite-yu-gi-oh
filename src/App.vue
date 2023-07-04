<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
const apiSpecies = `${endpoint}/types1`;
import { store } from './assets/data/store';

export default {
  name: 'Pokévuex',
  components: { AppMain },

  computed: {},

  methods: {
    fetchPokemon(url) {
      axios.get(url)
        .then(res => {
          store.isLoading = true;
          store.pokemon = res.data.docs;
        }).catch(err => {
          console.err(err.message);
        }).then(() => {
          store.isLoading = false;
        })
    }
  },

  mounted() {
    // Load unfiltered result
    this.fetchPokemon(endpoint)

    // Load type_01 API
    axios.get(apiSpecies)
      .then(res => {
        store.species = res.data;
      })
  },

};
</script>

<template>
  <!-- AppMain -->
  <AppMain />
</template>

<style lang="scss">
@use './assets/scss/style.scss';
</style>