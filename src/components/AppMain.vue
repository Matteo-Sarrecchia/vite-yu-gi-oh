<script>
import { store } from '../store';
import AppCard from './AppCard.vue';
import AppSearch from './AppSearch.vue';
export default {
    name: "AppMain",
    components: {
        AppCard,
        AppSearch
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main>
        <div class="container">
            <AppCard v-for="card in store.cardList" :details="card" />
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

main {
    display: flex;
    background-color: #D48F38;
    min-height: 100px;

    .container {
        width: 80%;
        margin: 20px auto;
        border: 1px solid black;
        background-color: white;
        display: flex;
        flex-wrap: wrap;
    }
}
</style>
