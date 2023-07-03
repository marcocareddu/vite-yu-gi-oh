<script>
import { store } from '../assets/data/store';
export default {
    data() {
        return { store }
    }
};
</script>

<template>
    <div v-for="pokemon in store.pokemon" class="col col-3 g-3 ">
        <div class="card rounded-5">
            <div class="img-contain">
                <img :src="pokemon.imageUrl" class="card-img-top img-fluid rounded-5" :alt="pokemon.name">
            </div>
            <div class="card-body text-center">
                <p class="card-text">{{ pokemon.number }}</p>
                <h5 class="card-text">{{ pokemon.name }}</h5>
                <p class="card-text">{{ pokemon.type1 }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
img {
    height: 200px;
    object-fit: contain;
}
</style>