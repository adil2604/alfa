<template>
  <div>
    <VmHero></VmHero>
    <VMMain></VMMain>
  </div>
</template>

<script>
import VMMain from '@/components/main/Main'
import VmProductsList from '@/components/products_list/ProductsListContainer';
import VmHero from '@/components/hero/Hero';

export default {
  name: 'index',
  components: {
    VmProductsList,
    VmHero,
    VMMain
  }
};
</script>
