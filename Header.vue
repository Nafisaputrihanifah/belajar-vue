<script setup>
import { Carousel } from 'flowbite-vue'
const pictures = [
  {
    'src': 'https://penerbitbuku.co.id/wp-content/uploads/2019/03/Toko-Buku-Online-Terbaik-di-Indonesia.jpg',
    'alt': 'Picture 1',
  },
  {
    'src': 'https://bukukampungku.com/wp-content/uploads/2022/07/Toko-Buku-Online-Terpopuler.jpg',
    'alt': 'Picture 2',
  },
  
]
</script>
<template>
  <Carousel :pictures="pictures"></Carousel>
</template>
