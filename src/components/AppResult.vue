<script>
import { store } from '../store';
export default {
    name: "AppResult",
    data() {
        return {
            store
        }
    },
    computed: {
    resultNumber (){
      return store.cardList.length
    }
  }
}
</script>

<template>
    <div>
        {{ resultNumber }}
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";

</style>
