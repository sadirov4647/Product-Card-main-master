<template>
  <div class="home">

    <ProductDescriptionDrawer
    :product="product"
    :active="active.product_drawer"
    @close-product-drawer="closeProductDrawer()"
    />

    <div class="product-cards__container">
      <ProductSummaryCard
      v-for="product in items"
      :key="product.id"
      :product="product"
      @view-product="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import items from '../data/item'
import ProductSummaryCard from '../components/products/ProductSummaryCard.vue'
import ProductDescriptionDrawer from '@/components/products/ProductDescriptionDrawer.vue';

export default {
  name: "Home",
  components: {
    ProductSummaryCard,
    ProductDescriptionDrawer
  },
  data(){
    return {
      items:items,
      product:null,
      active:{
        product_drawer:false
      }
    }
  },
  methods:{
    viewProduct(product){
      this.product = product
      this.active.product_drawer = true
      console.log(this.product);
    },
    closeProductDrawer(){
      this.active.product_drawer = false
    }
  }
};
</script>

<style>
  .product-cards__container{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>
