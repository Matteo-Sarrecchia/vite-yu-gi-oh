<script>

export default {
    name: "AppHeader"
}
</script>

<template>
    <header>
        <img src="../../public/yugioh-logo-yu-gi-oh-the-art.jpg" alt="">
        <h1>Yu-Gi-Oh Api</h1>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

header {
    display: flex;
    border: 1px solid black;
    padding: 10px;

    img {
        height: 50px;
    }
}
</style>
