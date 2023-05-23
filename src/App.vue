<script>
import AppHeader from "./components/AppHeader.vue";
import AppList from "./components/AppList.vue";
import AppLoading from "./components/AppLoading.vue";
import AppType from "./components/AppType.vue";
import { store } from "./store";
import axios from "axios";
export default {
  data() {
    return {
      store,
      isLoading: true,
    };
  },
  components: {
    AppType,
    AppList,
    AppHeader,
    AppLoading,
  },
  methods: {
    loadData() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((response) => (this.store.AppList = response.data.data));
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => (this.store.listArchetype = response.data));
    },
  },
  created() {
    setTimeout(() => {
      this.loadData();
    }, 1900);
    setTimeout(() => {
      this.isLoading = false;
    }, 2000);
  },
};
</script>

<template>

  <AppHeader />

 
  <main>
    <AppType />
    <div class="cards_list">
      <!-- componente Lista con dentro componente card e founded  -->
      <AppList />
      <AppLoading v-if="isLoading" />
    </div>
  </main>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
main {
  background-color: #d48f38;
  padding-bottom: 3rem;
  .cards_list {
    background-color: white;
    max-width: 1000px;
    margin: auto;
    padding: 3rem;
  }
}
</style>

