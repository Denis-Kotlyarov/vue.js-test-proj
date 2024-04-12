<template>
  <div class="container">
    <router-link :to="{ name: 'catalog' }">
      <div class="v-cart__link waves-effect waves-light btn">CATALOG</div>
    </router-link>

    <p class="v-cart__side-title" v-if="!CART.length">Looks like the cart is empty...</p>

    <p class="title" v-if="CART.length">CART</p>
    <i class="icon meduim material-icons">local_grocery_store</i>
    <div class="v-cart">
      <vCartItem
        v-for="(item, index) in CART"
        :key="item.article"
        :cart_item_data="item"
        @deleteFromCart="deleteFromCart(index)"
      />
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
import vCartItem from './v-cart-item.vue'
export default {
  name: 'v-cart',
  components: {
    vCartItem
  },
  props: {
    // cart_data: {
    //   typeof: Array,
    //   default() {
    //     return []
    //   }
    // }
  },
  data() {
    return {}
  },
  computed: {
    ...mapGetters(['CART'])
  },
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
  align-items: center;
}
.title {
  margin: 10px;
  margin-top: 23px;
}
.v-cart {
  max-height: 500px;
  overflow: auto;
}
/* .v-cart::-webkit-scrollbar {
  width: 0;
} */
.v-cart__link {
  text-align: center;
  margin-bottom: 10px;
}
.v-cart__side-title {
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: center;
}
.icon {
  margin-bottom: 10px;
}
</style>
