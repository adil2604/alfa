<template>
  <div>
    <div class="navbar-item">
      <b-dropdown id="dropdown-1" text="Товары" class="m-md-2">
        <b-dropdown-item><a href="#">Компьютеры</a></b-dropdown-item>
        <b-dropdown-item><a href="#">Комплектующие</a></b-dropdown-item>
        <b-dropdown-item><a href="#">Периферия</a></b-dropdown-item>
        <b-dropdown-item><a href="#">Электроника</a></b-dropdown-item>
        <b-dropdown-item><a href="#">Телефоны</a></b-dropdown-item>
      </b-dropdown>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VmMenu',
  data() {
    return {
      wishlistLabel: 'Wishlist',
      logoutLabel: 'Log out',
      loginLabel: 'Log in',
      signupLabel: 'Sign up'
    }
  },

  computed: {
    isUserLoggedIn() {
      return this.$store.getters.isUserLoggedIn;
    },
    getUserName() {
      let name = this.$store.getters.getUserName;

      if (name === '') {
        return 'user';
      } else {
        return name;
      }
    }
  },

  methods: {
    logout() {
      this.$store.commit('isUserLoggedIn', false);
      this.$store.commit('isUserSignedUp', false);
      this.$store.commit('removeProductsFromFavourite');

      // redirect to homepage
      this.$router.push({name: 'index'});
    },
    showLoginModal() {
      this.$store.commit('showLoginModal', true);
    },
    showSignupModal() {
      this.$store.commit('showSignupModal', true);
    }
  }
}
</script>
<style>
#dropdown-1{
  width:12rem;
  border-radius: 4px;
}
.btn-secondary{
    background-color: #BC090C;

}
</style>
