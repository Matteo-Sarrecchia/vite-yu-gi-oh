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

      if (store.searchText !== "All") {
        myUrl += `&${store.apiNameParameter}=${store.searchText}`

      } else myUrl

      axios.get(myUrl)
        .then(res => {
          store.cardList = res.data.data
          console.log(res.data.data);
        })
        .catch(err => {
          console.log(err)
        })
    },
    getArchetype() {

      axios.get(store.archetypeApiURL)
        .then(res => {
          store.archetypeList = res.data
        })
        .catch(err => {
          console.log(err)
        })
    }
  },
  created() {
    this.getCards();
    this.getArchetype();
  }
}
</script>

<template>
  <AppHeader />
  <!-- <AppSearch @mysearch="getCards" /> -->
  <AppSearch @mysearch="getCards" />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
