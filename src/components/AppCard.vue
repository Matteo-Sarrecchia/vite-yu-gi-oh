<script>

export default {
    name: "AppCard"
}
</script>

<template>
    <div class="container-card">
        immagine
        <a href="">
            titolo
        </a>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

.container-card {
    width: calc(100% / 5);
    height: 100px;
    border: 1px solid black;
    text-align: center;
}
</style>
