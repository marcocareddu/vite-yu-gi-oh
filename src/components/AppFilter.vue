<script>
export default {
    props: { typeToSearch: Array },
    data() {
        return {
            stringToSearch: '',
            elementToSearch: '',
        }
    },
    emits: ['string-to-search', 'element-to-search', 'form-submit']
}
</script>

<template>
    <div class="search-bar d-flex justify-content-center m-3">
        <form @submit.prevent="$emit('form-submit')">
            <input type="text" v-model.trim="stringToSearch" @keyup="$emit('string-to-search', stringToSearch)">
            <select v-model.trim="elementToSearch" @keyup.enter="$emit('element-to-search', elementToSearch)">
                <option value="">--</option>
                <option v-for="element in typeToSearch" :key="element" :value="element">{{ element }}</option>
            </select>
        </form>
    </div>
</template>

<style scoped></style>