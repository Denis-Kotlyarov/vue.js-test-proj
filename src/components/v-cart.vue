<template>
  <div class="container">
    <p class="title">CART</p>
    <div class="v-cart">
      <vCartItem
        v-for="(item, index) in cart_data"
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
      />
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
import vCartItem from './v-cart-item.vue'
export default {
  name: 'v-cart',
  components: {
    vCartItem
  },
  props: {
    cart_data: {
      typeof: Array,
      default() {
        return []
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    ...mapActions(['DELETE_FROM_CART']),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index)
    }
  },
  watch: {}
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
}
.title {
  margin: 20px;
  margin-top: 53px;
}
.v-cart {
  max-height: 500px;
  overflow: auto;
}
/* .v-cart::-webkit-scrollbar {
  width: 0;
} */
</style>
