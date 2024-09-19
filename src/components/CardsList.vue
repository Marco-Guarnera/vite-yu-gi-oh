<script>
import axios from "axios";
import CardsListItem from "./CardsListItem.vue";

export default {
    name: "CardsList",
    components: {
        CardsListItem
    },
    data: () => ({
        apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
        // Struttura dati
        cardsList: []
    }),
    methods: {
        getCardsList() {
            axios.get(this.apiUrl).then(response => {
                this.cardsList = response.data.data;
            });
        }
    },
    created() {
        this.getCardsList();
    }
}
</script>

<template>
    <div class="row g-0">
        <CardsListItem v-for="card in cardsList" :key="card.id" :src="card.card_images[0].image_url" :name="card.name"
            :type="card.archetype" />
    </div>
</template>

<style lang="scss" scoped>
.row {
    justify-content: center;
    gap: 1.5rem;
}
</style>