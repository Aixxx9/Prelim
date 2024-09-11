<template>
  <div>
    <h1>Item List</h1>
    <div v-for="item in filteredItems" :key="item.id">
      <Item :item="item" @add-to-cart="handleAddToCart" />
    </div>
  </div>
</template>

<script>
import Item from './Item.vue';

export default {
  components: {
    Item,
  },
  data() {
    return {
      items: [
        { id: 1, name: 'Item 1', price: 10, isVisible: true },
        { id: 2, name: 'Item 2', price: 20, isVisible: false },
        { id: 3, name: 'Item 3', price: 30, isVisible: true },
      ],
    };
  },
  computed: {
    filteredItems() {
      return this.items.filter(item => item.isVisible);
    },
  },
  methods: {
    handleAddToCart(item) {
      console.log(`Item added to cart: Name - ${item.name}, Price - ${item.price}`);
    },
  },
};
</script>

<style scoped>

</style>
