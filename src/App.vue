<script>
import { store } from "./store"
import axios from "axios"
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import AppSearch from './components/AppSearch.vue'

export default {
  components: {
    AppHeader,
    AppMain,
    AppSearch
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCards() {

      let myUrl = store.apiURL;

      if (store.searchText === "Alien") {
        myUrl += `&${store.apiNameParameter}=${store.searchText}`
      }

      axios.get(store.apiURL)
        .then(res => {
          store.cardList = res.data.data
          console.log("ok");
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <AppHeader />
  <AppSearch @mysearch="getCards" />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
