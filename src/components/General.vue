<template>
  <div id="general">
    <NewUnit @clicked="getUnitData" :isFirst="isFirst"/>
    <Convert @clicked="getValueToConvert"/>
    <Unit v-for="(item, index) in units" v-bind:key="index" v-bind:name="item.name" v-bind:multiplier="item.multiplier" :rawValue="value"/>
    <button id="reset" v-on:click="reset">Reset</button>
  </div>
</template>

<script>
import Unit from './Unit.vue'
import NewUnit from './NewUnit.vue'
import Convert from './Convert.vue'


export default {
  name: 'General',
  components: {
    Unit,
    NewUnit,
    Convert
  },

  data: function() {
    return {
      units: [],
      value: "1",
      isFirst: true
    }
  },

  methods: {
    getUnitData: function(name, multiplier){
      this.units.push({name: name, multiplier: multiplier})
      if (this.units.length!==0) {
        this.isFirst=false
      }
      
    },

    getValueToConvert: function(value){
      this.value=value
    },

    reset: function(){
      this.units=[]
      this.isFirst= true
    }

  }
}
</script>

<style>

  #reset{
    margin-top: 100px
  }


</style>
