<template lang="ru">
  <div class="row">
  <product class="product"
  v-for="product in products"
  :key="product.id"
  :product ="product"
  />
    </div>
</template>
<script>
import Product from "@/components/Product";
export default {
  components:{
  Product,
  },
    props:{
        products:{
            type: Array,
            required: true,
        }
    },
  data(){
    return{
    }
  },
}
</script>
<style lang="">
    
</style>