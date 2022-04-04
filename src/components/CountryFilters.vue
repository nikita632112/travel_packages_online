<template lang="ru">
            <div class="col-xl-3 col-lg-4 col-md-5">
            <div class="filter-sidebar">
              <div class="filter-sidebar-header">Страны:</div>
              <div class="filter-sidebar-content" >
                <div class="form-check" v-for="filter in filters">
                  <input class="form-check-input" type="radio" name="country" id="country-0" :value="filter.value" v-model="modelValue" @change="changValue" >
                  <label class="form-check-label" for="country-0">
                    {{filter.country}}
                  </label>
                </div>
              </div>
            </div>
          </div>
</template>
<script>
export default {
  name:"CountryFilters",
  props: {
    filters: {
      type: Array,
    },
    modelValue: {
      type: String
    },
  },
  methods: {
    changValue(event) {
      this.$emit('update:modelValue', event.target.value);
    }
  }
}
</script>
<style lang="" scoped>

</style>