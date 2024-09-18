<script>
import CardsList from "./CardsList.vue";

export default {
    components: {
        CardsList
    }
}
</script>

<template>
    <!-- Main -->
    <main>
        <CardsList />
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/partials/color-variables" as *;

main {
    background-color: $main-background-color;
}
</style>