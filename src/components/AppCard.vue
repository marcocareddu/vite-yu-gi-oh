<script>
import { store } from '../assets/data/store';
export default {
    data() {
        return { store }
    }
};
</script>

<template>
    <div v-for="pokemon in  store.pokemon" :key="pokemon.id" class="col col-3 g-3 ">

        <!-- Active change class -->
        <div class="card rounded-5" :class="pokemon.type1.toLowerCase()">
            <div class="img-contain py-3 d-flex justify-content-center align-item-center">
                <img :src="pokemon.imageUrl" class="card-img-top img-fluid rounded-circle" :alt="pokemon.name">
            </div>
            <div class="card-body text-center">
                <p class="card-text">{{ pokemon.number }}</p>
                <h5 class="card-text">{{ pokemon.name }}</h5>
                <p class="card-text">{{ pokemon.type1 }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Images */
img {
    height: 200px;
    max-width: 200px;
    object-fit: cover;
}

/* Card-type class */
.grass {
    background-color: darkseagreen;
}

.fire {
    background-color: darksalmon;
}

.water {
    background-color: aquamarine;
}
</style>