<script setup>
import axios from 'axios'
import {reactive} from 'vue';
import Navigation from "./components/Navigation.vue";
import Contenu from "./components/Contenu.vue";

let search='' 
if (window.location.search){
  const params=new URLSearchParams(window.location.search);
  search=params.get("s")
}
const state = reactive({
  data: {},
  search
})
axios.get(`https://www.thecocktaildb.com/api/json/v1/1/search.php?s=${state.search}`)
  .then( (res)=> {
  console.log(res)
  if (res.data) {
  state.data = res.data
  }
  })

</script>

<template>
  <div id="app">
    <img alt="TheCocktailDB logo" src="./assets/logo.png">
    <h1 class="mb-5">Bienvenue chez TheCocktailDB!</h1>
    <navigation></navigation>
    <contenu :drinks="state.data.drinks" ></contenu>
  </div>
</template>

<style>
html {
  background-color: #FFFAFA;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1 {
  padding-top: 4rem;
  color: #000000;
}
</style>
