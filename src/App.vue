<template>
  <div class="app">
    <Header/>
    <section class="site-main mb-5">
      <div class="container">
        <div class="row">
  <country-filters
      :filters="filters"
      v-model="value"/>
        <div class="col-xl-9 col-lg-8 col-md-7">
          <div class="filter-bar">
              <CityFilters v-model="search"/>
          </div>
          <section class="lattest-product-area pb-40 category-list" style="margin-left: 20px;">
            <div class="row">
          <product-list :products="filteredCity" @add="addProduct"/>
            </div>
              </section>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Header from "../src/views/Header.vue";
import ProductList from "@/components/ProductList";
import CountryFilters from "@/components/CountryFilters";
import CityFilters from "@/components/CityFilters";


export default {
  components: {
    Header, ProductList,CountryFilters,CityFilters,
  },
  data() {
    return {
      products: [
        {id: 1, img: '1.jpg', country: "Россия", title: "Сочи", price: "200 000"},
        {id: 2, img: '2.jpg', country: "Франция", title: "Париж", price: "150 000"},
        {id: 3, img: '3.jpg', country: "Тайланд", title: "Бангкок", price: "50 000"},
        {id: 4, img: '6.jpg', country: "Россия", title: "Санкт-Петербург", price: "150 000"},
        {id: 5, img: '4.jpg', country: "Тайланд", title: "Пхукет", price: "60 000"},
        {id: 6, img: '5.jpg', country: "Россия", title: "Москва", price: "250 000"},
       ,
      ],
      filters:[
        {value:"all",country: "Все (21)"},
        {value:"Россия",country: "Россия(10)"},
        {value:"Франция",country: "Франция(5)"},
        {value:"Тайланд",country: "Тайланд(6)"},
      ],
      search: "",
      value: "all",
      cart:[

      ],
    }
  },
  methods:{
    addProduct(product){
      this.cart.push(product);
    }
  },
  computed: {
    filteredCity() {
      return this.filteredCountry.filter(product => {
        return product.title.toLowerCase().indexOf(this.search.toLowerCase()) > -1
      })
    },
    filteredCountry() {
      if(this.value != "all")
      return this.products.filter(product => {
        return product.country.indexOf(this.value) > -1
      })
      else
        return this.products
    }
  }
}
</script>

<style lang="sass">

</style>
