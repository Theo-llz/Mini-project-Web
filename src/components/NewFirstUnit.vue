<template>
  <div id="newfirstunit">
    <input v-model="name">
    <button v-on:click="addUnit">
      + ADD
    </button>
  </div>
</template>

<script>
export default {
  name: 'NewFirstUnit',
  el: '#newfirstunit',
  data: function() {
    return {
      name: '',
      multiplier: '1'
    }
  },
  methods: {
    addUnit: function() {
      this.$emit("clicked", this.name, this.multiplier)
      this.name=''
      this.multiplier=''
    }
  }
}
</script>

<style>

</style>
