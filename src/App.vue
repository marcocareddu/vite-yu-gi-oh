<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import { store } from './assets/data/store';

export default {
  name: 'Pokévuex',
  components: { AppMain },

  created() {
    axios.get(endpoint)
      .then(res => {
        store.isLoadiung = true;
        store.pokemon = res.data.docs;
      }).catch(err => {
        console.err(err.message);
      }).then(() => {
        store.isLoadiung = false;
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