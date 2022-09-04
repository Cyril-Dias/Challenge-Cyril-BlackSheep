<script setup>
import {defineProps} from 'vue'
defineProps(["revele","closeModale","product"])
</script>

<template>
  <div class="bloc-modale" v-if="revele">
    <div class="overlay" v-on:click="closeModale"></div>
    <div class="modale card">
      <div v-on:click="closeModale" class="btn-modale btn btn-danger">X</div>
      <div class="ingredients">{{product.strIngredient1}} {{product.strIngredient2}} {{product.strIngredient3}}</div> 
    </div>
  </div>
</template>

<style scoped>
.bloc-modale {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.overlay {
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

.modale {
  background: #f1f1f1;
  color: #333;
  padding: 50px;
  position: fixed;
  top: 30%;
}

.btn-modale {
  position: absolute;
  top: 10px;
  right: 10px;
}
.ingredients {
  display: flex;
  flex-wrap: wrap;
  padding-top: 1rem;
  color: #000000;
}
</style>