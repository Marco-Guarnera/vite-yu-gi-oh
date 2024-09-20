<script>
import axios from "axios";
import CardsListItem from "./CardsListItem.vue";
import CardsListSelect from "./CardsListSelect.vue";

export default {
    name: "CardsList",
    components: {
        CardsListItem,
        CardsListSelect
    },
    data: () => ({
        apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=25&offset=0",
        // Struttura dati
        cardsList: []
    }),
    methods: {
        getCardsList(query) {
            if (query !== "All") {
                axios.get(this.apiUrl, {
                    params: {
                        archetype: query
                    }
                }).then(response => {
                    this.cardsList = response.data.data;
                });
            } else {
                axios.get(this.apiUrl).then(response => {
                    this.cardsList = response.data.data;
                });
            }
        }
    },
    created() {
        this.getCardsList();
    }
}
</script>

<template>
    <CardsListSelect @selectInput="getCardsList" />
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