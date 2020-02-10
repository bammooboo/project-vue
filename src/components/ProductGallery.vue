<template>
  <div class="product-gallery">
    <img class="product-gallery__image" src="../assets/gameboy-image.jpg" :alt="title"/>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    }
  }
}
</script>

<style lang="scss" scoped>
.product-gallery {
  width: 100%;

  &__image {
    width: 100%;
  }

  @media (min-width: 768px) {
    width: 50%;
  }
}
</style>