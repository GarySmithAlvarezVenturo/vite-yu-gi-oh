<script>
export default {};
</script>

<template>
  <div class="icon-container">
    <i class="fa-solid fa-circle-notch"></i>
  </div>
</template>

<style lang="scss" scoped>
.icon-container {
  display: flex;
  justify-content: center;

  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  .fa-circle-notch {
    font-size: 5rem;
    text-align: center;
    animation: spin 1.5s infinite linear;
    padding: 5rem;
  }
}
</style>