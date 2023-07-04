<script>
export default {
    props: { typeToSearch: Array },
    data() {
        return {
            stringToSearch: '',
            elementToSearch: '',
        }
    }
}
</script>

<template>
    <div class="searh-bar d-flex justify-content-center m-3">
        <input type="text" v-model.trim="stringToSearch" @keyup.enter>
        <select name="" id="" v-model="elementToSearch">
            <option value="--">--</option>
            <option v-for="element in typeToSearch" :key="element" :value="element">{{ element }}</option>
        </select>
    </div>
</template>

<style scoped></style>