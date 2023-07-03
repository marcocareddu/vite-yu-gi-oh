<script>
export default {
  name: 'Pokévuex',

};
</script>

<template>
  <main class="container">

    <!-- Header -->
    <header class="text-center">
      <h1>PokéVuex</h1>
    </header>

    <!-- Section -->
    <section class="card-box rounded-3 d-flex justify-content-center align-items-center p-5">
      <div class="card-container rounded-3 h-100 w-100 row">

        <!-- Card / Col -->
        <!-- !TO INJECT -->
        <div class="col col-3 g-3 ">
          <div class="card rounded-5">
            <img src="https://picsum.photos/200" class="card-img-top img-fluid rounded-5" alt="...">
            <div class="card-body text-center">
              <p class="card-text">Number</p>
              <h5 class="card-text">Name</h5>
              <p class="card-text">Type1</p>
            </div>
          </div>
        </div>

      </div>
    </section>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss';
</style>