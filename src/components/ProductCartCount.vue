<template>
  <div class="product-cart-count">
    <svg class="product-cart-count__icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 475.293 475.293"><path d="M475.293 178.235h-80.708l-84.791-141.32c-4.206-7.02-13.33-9.312-20.379-5.091-7.035 4.221-9.312 13.344-5.091 20.379l75.619 126.032H115.351L190.97 52.202c4.221-7.035 1.944-16.158-5.091-20.379-7.064-4.221-16.158-1.929-20.379 5.091l-84.791 141.32H0v29.706h32.237l37.734 201.283c3.945 21.076 22.366 36.364 43.805 36.364h247.742c21.438 0 39.859-15.288 43.79-36.349l37.747-201.298h32.239l-.001-29.705zM376.109 403.77c-1.305 7.02-7.441 12.112-14.592 12.112H113.776a14.86 14.86 0 01-14.606-12.126L62.451 207.94h350.392l-36.734 195.83z"/></svg>
    <p class="product-cart-count__count">{{ quantity }}</p>
  </div>
</template>

<script>
export default {
  props: {
    quantity: {
      type: Number
    }
  }
}
</script>

<style lang="scss" scoped>
.product-cart-count {
  color: #fff;
  height: 50px;
  position: absolute;
  right: 0;
  top: 0;
  width: 50px;

  &__icon {
    fill: #fff;
    padding-top: 1.5rem;
    position: absolute;
    width: 30px;
  }

  &__count {
    background-color: #fff;
    border-radius: 50%;
    color: #01749b;
    font-size: 12px;
    height: 16px;
    padding: 0.25rem;
    position: absolute;
    right: 0.5rem;
    text-align: center;
    top: 0.25rem;
    width: 16px;
  }
}
</style>