<script>
export default {
    name: "CardsListItem",
    props: {
        src: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        type: {
            type: String,
            required: false
        }
    }
}
</script>

<template>
    <div class="col-2">
        <!-- Card -->
        <div class="card">
            <img :src="src" :alt="name" class="card-img-top">
            <div class="card-body">
                <h3 class="card-title" v-text="name"></h3>
                <span class="card-text" v-text="type"></span>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/color-variables" as *;

.card {
    height: 425px;
    background-color: $primary-color;

    .card-body {
        text-align: center;

        h3 {
            color: #FFF;
            font-size: 1rem;
            font-weight: bold;
        }

        span {
            color: #000;
        }
    }
}
</style>