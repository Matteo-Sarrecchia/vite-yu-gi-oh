<script>
import { store } from '../store';
export default {
    name: "AppSearch",
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
            <select v-model="store.searchText" class="form-select" aria-label="Default select example">
                <option value="All">All</option>
                <!-- <option value="1" @click.prevent="$emit('mysearch')">Alien</option> -->
                <option v-for="elm in store.archetypeList" :value="elm.archetype_name" @click.prevent="$emit('mysearch')">
                    {{ elm.archetype_name }}
                </option>
            </select>
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

        select {
            width: 30%;
        }
    }

}
</style>
