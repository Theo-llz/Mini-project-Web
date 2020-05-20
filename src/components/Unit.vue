<template>
  <div class="unit">
    {{value}}
    {{name}}
    
  </div>
</template>

<script>
export default {
  name: 'Unit',
  props: {
    name: String,
    multiplier: String,
    rawValue: String
  },

  data: function() {
    return {
      value: "1"
    }
  },

  beforeMount() {
    this.value = this.rawValue * this.multiplier
  },

  watch:{
    rawValue:function(){
      this.value = this.rawValue * this.multiplier
    }
  }

}
</script>

<style>
  .unit{
    margin-top: 50px;
    font-size: 50px;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
</style>
