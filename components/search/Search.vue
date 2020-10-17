<template>
  <p class="control has-icons-right">

    <input
        class="input search"
        type="text"
        v-model="value"
        :placeholder="placeholder"
        @keyup="search(value)"
    >
    <span class="icon is-small is-right">
			<i class="fa fa-search"></i>
		</span>
  </p>
</template>

<script>
export default {
  name: 'search',
  data() {
    return {
      value: ''
    }
  },

  computed: {
    placeholder() {
      if (this.$route.path === '/wishlist') {
        return 'Search in wishlist...';
      } else {
        return 'Поиск...';
      }
    }
  },

  methods: {
    search(value) {
      if (value.length > 0) {
        this.$store.commit('setHasUserSearched', true);
        this.$store.commit('setProductTitleSearched', value);
      } else {
        this.$store.commit('setHasUserSearched', false);
        this.$store.commit('setProductTitleSearched', '');
      }
    }
  }
}
</script>
<style>
.search {
  width: 20rem;
  height: 2.4rem;
  background-color: #D7D7D7;
}
</style>
