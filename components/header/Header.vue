<template>
  <div class="header">
    <div class="row red">
      <div class="container d-flex justify-content-between align-items-center">
        <p style="text-decoration: underline" class="ml-4">Алматы</p>
        <p style="text-decoration: underline">
          <b-icon-person-fill></b-icon-person-fill>
          Кабинет
        </p>

      </div>
    </div>
    <nav class="container" aria-label="main navigation">
      <div class="row ">
        <div class="navbar-brand">
          <nuxt-link :to="{ name: 'index' }" class="navbar-item">
            <h1 class="title is-3 is-flex-mobile"></h1>
          </nuxt-link>

          <a role="button" class="navbar-burger burger" @click="isMenuOpen = !isMenuOpen" aria-label="menu"
             aria-expanded="false">
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>

        <VmMenuProducts></VmMenuProducts>
          <div class="navbar-item ">
            <VmSearch class="mb-1"></VmSearch>
          </div>


        <div class="navbar-menu is-active">
          <div class="navbar-start">

          </div>

          <div class="navbar-end">
            <div class="navbar-item" style="width: 9rem;">
            <b-button block variant="primary">+ Подать</b-button>
          </div>
            <div class="navbar-item shopping-cart" @click="showCheckoutModal">
            <span class="icon">
              <i class="fa fa-shopping-cart"></i>
            </span>
              <span :class="[numProductsAdded > 0 ? 'tag is-info' : '']">{{ numProductsAdded }}</span>
            </div>

          </div>
        </div>

        <!-- For mobile and tablet -->
<!--        <div v-show="isMenuOpen" class="navbar-end">-->
<!--          <VmMenu></VmMenu>-->
<!--        </div>-->

        <!-- For desktop -->

      </div>

    </nav>
  </div>
</template>

<script>
import VmMenu from '../menu/Menu';
import VmSearch from '../search/Search';
import VmMenuProducts from '../menu/MenuProducts';

export default {
  name: 'VmHeader',

  data() {
    return {
      linkedinTooltip: 'Follow us on Linkedin',
      facebookTooltip: 'Follow us on Facebook',
      twitterTooltip: 'Follow us on Twitter',
      instagramTooltip: 'Follow us on Instagram',
      isCheckoutActive: false,
      isMenuOpen: false
    }
  },

  components: {
    VmSearch,
    VmMenu,
    VmMenuProducts
  },

  computed: {
    numProductsAdded() {
      return this.$store.getters.productsAdded.length;
    }
  },

  methods: {
    showCheckoutModal() {
      this.$store.commit('showCheckoutModal', true);
    }
  }
};
</script>

<style lang="scss" scoped>
.title {
  background: url('../../static/k134.png') no-repeat;
  background-position: 50% 50%;
  background-size: 180px;
  width: 200px;
  height: 50px;
}

.shopping-cart {
  cursor: pointer;
}

a {
  color: grey;
}

p {
  color: white;
}

.red {
  background-color: #BC090C;
  height: 2.5rem;
}
.header{
  box-shadow: 0px 0px 35px 3px rgba(0, 0, 0, 0.25);
}
</style>
