<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-3" v-for="product in products" :key="product.id">
        <no-ssr>
          <VmProducts :product="product"></VmProducts>

        </no-ssr>
      </div>
      <div class="section" v-if="products.length === 0">
        <p>{{ noProductLabel }}</p>
      </div>
    </div>

  </div>
</template>

<script>
import VmProducts from '../Products';
import {getByTitle} from '@/assets/filters';

export default {
  name: 'productsList',

  components: {VmProducts},

  data() {
    return {
      id: '',
      noProductLabel: 'No product found',
      productsFiltered: []
    };
  },

  computed: {
    products() {
      if (this.$store.state.userInfo.hasSearched) {
        return this.getProductByTitle();
      } else {
        return this.$store.state.products;
      }
    }
  },

  methods: {
    getProductByTitle() {
      let listOfProducts = this.$store.state.products,
        titleSearched = this.$store.state.userInfo.productTitleSearched;

      return this.productsFiltered = getByTitle(listOfProducts, titleSearched);
    }
  }

};
</script>

<style lang="scss" scoped>
.card {
  margin: 10px;
}
</style>
