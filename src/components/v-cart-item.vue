<template>
  <div class="v-cart-item">
    <img
      class="v-cart-item__image"
      src="https://i.pinimg.com/originals/ef/8b/51/ef8b51455131b34cf2dcdde3ac9c5078.jpg"
      :alt="cart_item_data.name"
    />
    <div>
      <p class="v-cart-item__name">{{ cart_item_data.name }}</p>
      <p class="v-cart-item__price">{{ cart_item_data.price }}$</p>
      <p class="v-cart-item__article">{{ cart_item_data.article }}</p>
      <p class="v-cart-item__about">{{ cart_item_data.about }}</p>
    </div>
    <div class="v-cart-item__quantity">
      <p>
        Quantity: <span>{{ cart_item_data.quantity }}</span>
      </p>
      <button class="v-cart-item__btn" @click="deleteFromCart">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'v-cart-item',
  props: {
    cart_item_data: {
      typ: Object,
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
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  watch: {}
}
</script>

<style scoped>
.v-cart-item {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 grey;
  padding: 20px;
  margin: 20px;
}
.v-cart-item__image {
  width: 170px;
  border-radius: 20px;
}
.v-cart-item__price {
  font-size: 12px;
}
.v-cart-item__btn {
  margin-top: 20px;
  padding: 8px 16px;
  border-radius: 10px;
  transition: all 0.3s ease-in-out;
}
.v-cart-item__btn:hover {
  background: rgb(0, 0, 0);
  color: #ffffff;
}
.v-cart-item__about {
  max-width: 220px;
  font-size: 12px;
}
.v-cart-item__name {
  font-size: 16px;
  margin: 7px 0;
}
</style>
