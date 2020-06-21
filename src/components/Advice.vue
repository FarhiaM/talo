<template>
  <div class="advice">
    <button v-on:click="getAdvice()">Give me talo</button>
    <div v-if="talo">
      {{talo}}
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
 name: 'Advice',
 data() {
   return {
     talo: ''
   }
 },
 methods:{
   getAdvice(){
     axios.get('https://api.adviceslip.com/advice').then(response => {
       this.talo = response.data.slip.advice;
      });
   }
 }
}
</script>

<style>

</style>