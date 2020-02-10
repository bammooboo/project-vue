<template>
  <div class="product-form">
    <div class="product-form__inner">
      <h1 class="product-form__title">{{ title }}</h1>
      <p class="product-form__description">{{ description }}</p>
      <p class="product-form__price">£{{ price }}</p>
      <button 
        class="product-form__button"
        aria-label="addToBag"
        role="button"
        name="addToBag"
        tabindex="0"
        @click="addToBag"
      >
        ADD
      </button>
      <div class="product-form__notification">
        <p>{{ maxQuantityMessage }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    },
    description: {
      type: String
    },
    price: {
      type: Number
    },
    quantity: {
      type: Number
    },
    maxQuantityMessage: {
      type: String
    }
  },
  methods: {
    addToBag() {
      console.log('added to bag');
      this.$emit('cartCountIncreased', this.quantity);
    }
  },
}
</script>

<style lang="scss" scoped>
.product-form {
  color: #fff;
  width: 100%;

  &__inner {
    max-width: 500px;
    padding: 1.5rem;
    position: relative;
    top: -1rem;
  }

  &__title {
    margin-top: 0;
  }

  &__description,
  &__price {
    margin-bottom: 1.5rem;
  }

  &__button {
    align-items: center;
    appearance: none;
    background-color: #fff;
    border: 2px solid transparent;
    border-radius: 5%;
    box-shadow: none;
    color: #01749b;
    display: inline-flex;
    font-weight: 700;
    justify-content: center;
    letter-spacing: 1px;
    line-height: 1.2;
    margin-bottom: 1rem;
    min-height: 40px;
    padding: 0.75rem 1.5rem;
    text-align: center;
    text-decoration: none;
    user-select: none;
    white-space: nowrap;
    width: auto;

    &[disabled=true] {
      background-color: #808080;
      color: #d3d3d3;
    }
  }

  &__notification {
    background-color: #fff;
    border: 1px solid #cc0000;
    color: #cc0000;
    display: none;

    p {
      margin: 1rem;
    }

    &.show {
      display: block;
    }
  }

  @media (min-width: 768px) {
    width: 50%;
  }
}
</style>