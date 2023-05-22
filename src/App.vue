<script>
import AppHeader from "./components/AppHeader.vue";
import AppList from "./components/AppList.vue";
import AppType from "./components/AppType.vue";
import { store } from "./store";
import axios from "axios";
export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppType,
    AppList,
    AppHeader,
  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.AppList = response.data.data));
  },
};
</script>

<template>
  <!-- componente header  -->
  <AppHeader />

  <!-- sfondo arancione -->
  <main>
    <AppType />
    <div class="cards_list">
      <!-- componente Lista con dentro componente card e founded  -->
      <AppList />
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
  .cards_list {
    background-color: white;
    max-width: 1000px;
    margin: auto;
    padding: 3rem;
  }
}
</style>

