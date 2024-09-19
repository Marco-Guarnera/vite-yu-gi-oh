<script>
import CardsList from "./CardsList.vue";

export default {
    name: "AppMain",
    components: {
        CardsList
    }
}
</script>

<template>
    <!-- Main -->
    <main>
        <div class="container">
            <!-- Cards List -->
            <div id="cards-list">
                <CardsList />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/partials/color-variables" as *;

main {
    background-color: $primary-color;
    padding: 1.5rem 0;

    #cards-list {
        background-color: #FFF;
        padding: 1.5rem 0;
    }
}
</style>