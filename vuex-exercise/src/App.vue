<template>
  <div id="app">
    Parent counter : {{parentCounter}}
  

   <!-- Parent counter : {{this.$store.state.counter}} <br/>
   <button v-on:click="addCounter">+</button>
   <button v-on:click="subCounter">-</button> -->

   <!-- <child v-bind:passedCounter="counter"></child> -->
   <child></child>
  </div>
</template>

<script>
import {mapGetters} from 'vuex'
import Child from './Child';

export default {
  components : {
    'child' : Child
  },
  computed: {
    ...mapGetters({
      parentCounter : 'getCounter'
    })
  }
  // computed: {
  //   parentCounter() {
  //     return this.$store.getters.getCounter;
  //   }
  // }

  // data(){
  //   return {
  //     counter : 0
  //   }
  // },
  // methods: {
  //   addCounter() {
  //     this.$store.state.counter++;
  //   },
  //   subCounter() {
  //     this.$store.state.counter--;
  //   }
  // },
  // components : {
  //   'child' : Child
  // }
}
</script>

<style>

</style>
