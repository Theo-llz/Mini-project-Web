<template>
  <div class="convert">
    {{name}}
    <input id="thirdbox" v-model="value" placeholder="Value to convert">
    <button v-on:click="Conversion" id="convert">Convert</button>
  </div>
</template>

<script>
export default {
  name: 'convert',

  data: function() {
    return {
      name: '',
      value: ''
    }
  },
  methods: {
    Conversion: function() {
      this.$emit("clicked", this.value)
      this.value=''
    }
  }
}
</script>

<style>

  button {

  }

  input {
    height: 100px;
    width: 500px;
    font-size: 60px
  }

  input::placeholder{
    font-size: 60px;
    width: 100%;

  }

  #thirdbox{
    margin-top: 50px
  }

  #convert{
   margin-left: 100px;
   height: 50px;
   width: 200px;
  }
</style>
