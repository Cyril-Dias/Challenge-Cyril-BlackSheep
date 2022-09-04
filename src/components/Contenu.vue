<script setup>
import Modale from './Modale';
import Produit from './Produit';
import {reactive, defineProps, computed} from 'vue';

const props=defineProps(['drinks'])
const state=reactive({
  activeProduct: null 
  })
const activeProduct=computed(()=> {
  if(props.drinks) {
    return props.drinks.find((drink)=> {
    return drink.idDrink === state.activeProduct
  })
  }
  else{return null}
}) 
const closeModale= ()=> {
  state.activeProduct=null
}
const changeActiveProduct= (productId) => {
  state.activeProduct=productId
}
</script>

<template>
  <div class="container my-5">
    <div class="cards">
    <produit 
     class="produit"
     @click="() => {
      changeActiveProduct(drink.idDrink)
     }"
     v-for="drink in drinks" 
     :key="drink.idDrink" 
     :name="drink.strDrink"
     :image="drink.strDrinkThumb"
    />
    </div>
    <modale 
    :revele="activeProduct!=null" 
    :closeModale="closeModale"
    :product="activeProduct"
    />
  </div>
</template>

<style>
  .cards {
    display: flex;
    flex-wrap: wrap;
  }
  .btn {
    background: #FF4500;
    border-color: #FF8C00;
    }
</style>