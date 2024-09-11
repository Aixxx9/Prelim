<template>
  <div v-if="item.isVisible">
    <h2>{{ item.name }}</h2>
    <p>Price: ${{ item.price }}</p>
    <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToCart() {
      console.log(`Item added to cart: Name - ${this.item.name}, Price - ${this.item.price}`);
      this.$emit('add-to-cart', this.item);
    },
  },
};
</script>

<style scoped>

</style>
