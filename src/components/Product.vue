<template lang="">
<div class="card text-center card-product">
         <div class="card-product__img">
          <img :src=" require('../assets/img/' + product.img)" alt="Картинка товара">
         </div>
         <div class="card-body">
          <p>{{product.country}}</p>
          <h4 class="card-product__title">{{product.title}}</h4>
          <p class="card-product__price">{{product.price}} руб</p>
          <p><button type="button" class="btn btn-primary" @click.native="addProduct(product)">Заказать</button></p>
         </div>
        </div>
</template>
<script>
export default {
  data(){
    return {
    }
  },
    props:{
      product:{
        type:Object,
        required:true,
      }
    },
  methods:{
      addProduct(product){
        this.$emit('add', product)
      },
  }

}
</script>
<style lang="">
    
</style>