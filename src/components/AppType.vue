<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="select-container">
    <select @change="">
      <option
        v-for="option in store.listArchetype"
        :key="option.archetype_name"
        :value="option.archetype_name"
      >
        {{ option.archetype_name }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
.select-container {
  max-width: 1000px;
  margin: auto;
  select {
    padding: 0.5rem;
    margin: 1rem 0;
    font-size: 1.1em;
    font-weight: bold;
    border-radius: 5px;
  }
}
</style>


