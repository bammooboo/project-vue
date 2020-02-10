<template>
  <div class="product">
    <product-cart-count :quantity="quantity"></product-cart-count>
    <product-gallery :title="title"></product-gallery>
    <product-form
      :title="title"
      :description="description"
      :price="price"
      :quantity="quantity"
      :maxQuantityMessage="max_quantity_message"
      @cartCountIncreased="increaseCartCount"
    ></product-form>
  </div>
</template>

<script>
import ProductCartCount from './ProductCartCount.vue';
import ProductForm from './ProductForm.vue';
import ProductGallery from './ProductGallery.vue';

export default {
  data: function() {
    return {
      title: 'Gameboy Color - Blue',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      price: '159.99',
      quantity: 0,
      max_quantity: 2,
      max_quantity_message: 'You have reached the maximum quantity available'
    }
  },
  methods: {
    increaseCartCount() {
      if (this.quantity == this.max_quantity) {
        document.querySelector('.product-form__button').setAttribute('disabled', true);
        document.querySelector('.product-form__notification').classList.add('show');
        return;
      }
      this.quantity++;
    }
  },
  components: {
    ProductCartCount,
    ProductForm,
    ProductGallery
  }
}
</script>

<style lang="scss">
.product {
  align-items: center;
  background-color: #01749b;
  display: flex;
  flex-flow: column nowrap;
  font-family: 'Open Sans', sans-serif;
  margin: 1rem auto;
  max-width: 1440px;
  position: relative;
  width: 100%;

  @media (min-width: 768px) {
    flex-flow: row nowrap;
  }
}
</style>
