<template>
  <div class="advice">
    <img src="../assets/talo-logo.png"/>
    <button v-on:click="getAdvice()">Give me talo</button>
    <div class="talo" v-if="talo">
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

<style scoped>

.advice{
  display: flex;
  flex-direction: column;
  align-items: center;
}

img{
  height: 300px;
  width: 300px;
}

.talo{
  margin-left: 35px;
  margin-right: 35px;
  text-align: center;
  color: #1B4C33;
  font-size: 20px;
  margin-top: 40px;
}

button {
  height: 60px;
  width: 150px;
  background: #D1D4DE;
  border: none;
  border-radius: 30px;
  box-shadow: 0px 8px 15px #AFB3C5;
  transition: all 0.3s ease 0s;
  font-family: sans-serif;
  font-weight: 10;
  letter-spacing: 1px;
  cursor: pointer;
  transition-duration: 0.4s;
}

button:hover, button:focus{
  background-color: rgb(215, 109, 83);
  outline: 0;
}

@media (min-width: 768px) and (max-width: 1023px) {
 img{
  height: 500px;
  width: 500px;
}
}
@media (min-width: 1024px) {
 img{
  height: 700px;
  width: 700px;
}
}

</style>