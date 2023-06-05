<script>

export default {
    name: "AppCard",
    props: {
        details: Object
    }
}

</script>

<template>
    <div class="container-card">
        <div class="img-row" v-for="elm in details.card_images">
            <img :src="elm.image_url_small" alt="">
        </div>
        <div class="text-name">
            <a href="">
                {{ details.name }}
            </a>
        </div>
        <div class="text-type">
            {{ details.archetype }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

.container-card {
    width: calc(100% / 5 - 20px);
    min-height: 100px;
    text-align: center;
    margin: 10px;
    background-color: #D48F38;
    font-size: 14px;

    .img-row {
        min-height: 50px;

        img {
            padding: 10px;
        }
    }

    a {
        text-decoration: none;
        color: black;
        padding: 5px;

        &:hover {
            color: blue;
            border-bottom: 2px solid blue;
        }
    }

    .text-type {
        padding: 5px;
    }
}
</style>
