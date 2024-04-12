<template>
  <div class="v-catalog-item">
    <img
      class="v-catalog-item__image"
      :src="'/src/assets/images/' + product_data.image"
      :alt="product_data.name"
    />
    <h3 class="item__name">{{ product_data.name }}</h3>
    <p class="item__price">{{ product_data.price }}$</p>
    <p class="item__about">{{ product_data.about }}</p>
    <button class="item__btn" @click="addToCart">Add to cart</button>
  </div>
</template>

<script>
export default {
  name: 'v-catalog-item',
  components: {},
  props: {
    product_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    addToCart() {
      this.$emit('addToCart', this.product_data)
    }
  },
  watch: {}
}
</script>

<style>
.v-catalog-item__image {
  width: 200px;
  border-radius: 20px;
}
.v-catalog-item {
  background: white;
  min-width: 260px;
  padding: 15px;
  color: black;
  border-radius: 20px;
  text-align: center;
}
.item__price {
  font-size: 12px;
}
.item__btn {
  margin-top: 20px;
  padding: 8px 20px;
  border-radius: 10px;
  transition: all 0.3s ease-in-out;
}
.item__btn:hover {
  background: rgb(0, 0, 0);
  color: #ffffff;
}
.item__about {
  max-width: 220px;
  font-size: 12px;
}
.item__name {
  font-size: 18px;
}
</style>
