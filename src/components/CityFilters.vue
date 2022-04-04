<template>
  <div class="input-group">
  <input :value="modelValue"
         @input="updateInput"
         type="text" class="form-control"
         placeholder="Название города">
    </div>
</template>

<script>
export default {
  props: {
    modelValue:{
      type: String
    }
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style scoped>

</style>