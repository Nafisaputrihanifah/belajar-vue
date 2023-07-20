<script setup>
import {ref} from 'vue'

const msg = ("Hello Akatsuki");
const rawHtml = ("Pain");
</script>

<template>
  <div  id="app">
    
    <h1>{{ msg }}</h1>

    
    <p> {{ rawHtml }}</p>
    <p>
      <span v-html="rawHtml"></span>
    </p>
    <span style="color: rgb(255, 0, 0)">akatsuki</span>
    <button :disabled="isButtonDisabled">KLIK</button>

  </div>

 
 
</template>  