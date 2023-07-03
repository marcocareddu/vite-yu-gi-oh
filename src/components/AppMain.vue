<script>
import { store } from '../assets/data/store'
import AppCard from './AppCard.vue';
import AppLoader from './AppLoader.vue';

export default {
    components: { AppCard, AppLoader },
    data() {
        return { store }
    }
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