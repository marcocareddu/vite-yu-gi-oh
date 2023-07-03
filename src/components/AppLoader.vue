<script>

export default {

}

</script>

<template>
    <div class="overlay">
        <h1>Loading...</h1>
    </div>
</template>

<style scoped>
.overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background-color: rgba(146, 189, 226, 0.77);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
}
</style>