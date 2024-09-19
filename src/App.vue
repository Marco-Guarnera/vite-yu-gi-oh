<script>
import AppMain from "./components/AppMain.vue";

export default {
    name: "App",
    components: {
        AppMain
    }
}
</script>

<template>
    <AppMain />
</template>

<style lang="scss">
@use "../node_modules/bootstrap/scss/bootstrap.scss";
@use "./styles/generic.scss" as *;
</style>