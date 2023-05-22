<script>
import AppCard from "./AppCard.vue";
import AppFounded from "./AppFounded.vue";
import { store } from "../store";
export default {
  components: { AppFounded, AppCard },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div>
    <AppFounded />
    <div class="cards">
      <AppCard v-for="card in store.AppList" :key="card.id" :cardData="card" />
    </div>
  </div>
</template>

<style scoped>
.cards {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}
</style>