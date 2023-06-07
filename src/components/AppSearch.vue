<script>
import { store } from '../store';
import AppResult from './AppResult.vue'
export default {
    name: "AppSearch",
    components: {
        AppResult
    },
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <section class="search">
        <div class="container">
            <select v-model="store.searchText" class="form-select" aria-label="Default select example"
                @change="$emit('mysearch')">
                <option value="All">All</option>
                <!-- <option value="1" @click.prevent="$emit('mysearch')">Alien</option> -->
                <option v-for="elm in store.archetypeList" :value="elm.archetype_name">
                    {{ elm.archetype_name }}
                </option>
            </select>
            <div class="result">
                <span>Found</span>
                <AppResult />
                <span>cards</span>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

.search {
    background-color: #D48F38;

    .container {
        width: 80%;
        margin: 0 auto;
        padding-top: 20px;
        display: flex;

        select {
            width: 30%;
        }

        .result {
            width: 30%;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 1px solid black;
            background-color: black;
            color: white;
            margin-left: 50px;
            border-radius: 15px;

            span {
                padding: 0 10px;
            }
        }
    }

}
</style>
