<template>
  <div id="newunit">
    <input id="firstbox" v-model="name" placeholder="Unit">
    <input v-model="multiplier" v-bind:disabled="isFirst" placeholder="Multiplier">
    <button id="add" v-on:click="addUnit" v-bind:disabled="isNaN(multiplier)">
      + ADD
    </button>
  </div>
</template>

<script>
export default {
  name: 'NewUnit',
  el: '#newunit',
  props: {
    isFirst: Boolean
  },

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
  },

  watch:{
    isFirst:function(){
      if(this.isFirst===true){
        this.multiplier = "1"
      }
    }
  }

}
</script>

<style>

  

  input{
    border-radius: 20px
  }

  #firstbox{
    margin-right: 100px;
  }

  #add{
    height: 50px;
    width: 200px;
    margin-left: 100px
  }
</style>
