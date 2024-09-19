<script>
import axios from "axios";

export default {
    name: "CardsListSelect",
    data: () => ({
        apiUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
        // Struttura dati
        list: []
    }),
    methods: {
        getList() {
            axios.get(this.apiUrl).then(response => {
                this.list = response.data;
            });
        }
    },
    created() {
        this.getList();
    }
}
</script>

<template>
    <select class="form-select">
        <option selected>All</option>
        <option v-for="(item, i) in list" :key="i" v-text="item.archetype_name"></option>
    </select>
</template>

<style lang="scss" scoped>
select {
    width: 25%;
    margin: 0 auto 1.5rem auto;
}
</style>