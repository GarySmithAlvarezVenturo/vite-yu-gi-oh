<script>
export default {
  props: {
    cardData: Object,
  },
};
</script>

<template>
  <div class="card">
    <div class="img-container">
      <img :src="cardData.card_images[0].image_url_small" alt="image" />
    </div>
    <div class="text-container">
      <div class="title">{{ cardData.name.toUpperCase() }}</div>
      <div class="type">{{ cardData.archetype }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  background-color: #d48f38;
  width: calc((100% / 5) - 1rem);
  margin: 1rem 0.5rem;
  border-radius: 5px;
  padding-bottom: 0.5rem;
  cursor: pointer;
  .img-container {
    width: 100%;
    img {
      width: 100%;
    }
  }
  .text-container {
    width: 100%;
    font-size: 0.9em;
    text-align: center;
    .type {
      font-size: 0.7em;
      margin-top: 0.5rem;
    }
  }
  &:hover {
    transform: scale(1.1);
  }
}
</style>
