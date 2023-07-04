<script>
import axios from 'axios';
import { store } from '../assets/data/store'
import AppCard from './AppCard.vue';
import AppLoader from './AppLoader.vue';
import AppFilter from './AppFilter.vue'

export default {
    components: { AppCard, AppLoader, AppFilter },
    data() {
        return {
            store,
            selectedElement: '',
            selectedString: '',
            endpoint: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons',
        }
    },
    computed: {
        reloadLink() {
            return `${this.endpoint}?q[name]=${this.selectedString}&eq[type1]=${this.selectedElement}`
        },

        fetchPokemon() {
            axios.get(this.reloadLink)
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
}
</script>

<template>
    <!-- Display Overlay -->
    <AppLoader />
    <main class="container">

        <!-- Header -->
        <header class="text-center">
            <h1>PokéVuex</h1>
        </header>

        <!-- App Filter -->
        <AppFilter :type-To-Search="this.store.species" @string-to-search="selectedString = $event"
            @element-to-search="selectedElement = $event" @form-submit="fetchPokemon" />

        <!-- Section -->
        <section class="card-box rounded-3 d-flex justify-content-center align-items-center p-5">
            <div class="card-container rounded-3 h-100 w-100 row">

                <!-- AppCard / Col -->
                <AppCard />
            </div>
        </section>
    </main>
</template>

<style>
/* Main */
/* Header */
header {
    height: 80px;
}

.card-box {
    background-color: lightblue;
    height: 700px;
}

.card-container {
    background-color: lightgray;
    overflow-y: auto;
}
</style>