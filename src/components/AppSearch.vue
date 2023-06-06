<script>
import { store } from '../store';
export default {
    name: "AppSearch",
    props: {
        details: Object
    }
}

</script>

<template>
    <section class="search">
        <div class="container">
            <select class="form-select" aria-label="Default select example">
                <option value="0">All</option>
                <option value="1" @click.prevent="$emit('mysearch')">Alien</option>
                <option value="2"></option>

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
