<template>
  <div class="v-main-wrapper">
    <vCatalog />
    <vCart v-if="CART.length" :cart_data="CART" />
  </div>
</template>

<script>
import vCatalog from './v-catalog.vue'
import vCart from './v-cart.vue'
import { mapGetters } from 'vuex'

export default {
  name: 'v-main-wrapper',
  components: {
    vCatalog,
    vCart
  },
  props: {},
  data() {
    return {
      title: 'MAIN WRAPPER'
    }
  },
  computed: {
    ...mapGetters(['CART'])
  },
  methods: {},
  watch: {}
}
</script>

<style>
.v-main-wrapper {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  max-width: 1120px;
  margin: 0 auto;
}
</style>
