<script setup>
import {defineProps} from 'vue'
defineProps(['name','image'])
</script>
<template>
  <div>
    <p>{{name}}</p>
    <img class="imageProduit" :src="image"/>
  </div>
</template>
<style scoped>
    p {
        font-size: 2rem;
        color: black;
    }
    .imageProduit{
        height: 300px;
        width: 300px;
    }
</style>