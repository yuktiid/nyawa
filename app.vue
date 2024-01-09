<script setup lang="ts">
useSeoMeta({
  description: 'Nyawa adalah e-commerce fashion yang menyediakan berbagai macam produk fashion untuk pria, wanita, dan anak-anak. Kami menawarkan produk-produk berkualitas dengan harga yang terjangkau. Kami juga selalu update dengan tren fashion terbaru.',
  ogTitle: 'Tingkatkan Level Fashionmu: Temukan Tren & Brand Terpopuler di Nyawa.com',
  ogDescription: 'Nyawa hadir untuk memenuhi kebutuhan fashion Anda. Kami menyediakan berbagai macam produk fashion, mulai dari pakaian, sepatu, aksesoris, hingga perlengkapan fashion lainnya. Kami juga menyediakan berbagai macam pilihan ukuran dan warna untuk memenuhi kebutuhan Anda.',
  ogImage: '/logo.png',
  ogUrl: '[og:url]',
  twitterTitle: 'Tingkatkan Level Fashionmu: Temukan Tren & Brand Terpopuler di Nyawa.com',
  twitterDescription: 'Nyawa hadir untuk memenuhi kebutuhan fashion Anda. Kami menyediakan berbagai macam produk fashion, mulai dari pakaian, sepatu, aksesoris, hingga perlengkapan fashion lainnya. Kami juga menyediakan berbagai macam pilihan ukuran dan warna untuk memenuhi kebutuhan Anda.',
  twitterImage: '/logo.png',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'id'
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/logo.png'
    }
  ],
  titleTemplate: (titleChunk) => {
        // Gunakan titleChunk untuk mendapatkan judul dinamis
        return titleChunk ? `${titleChunk} - nyawa` : 'belum ada judulnya bro';
      }
    

})
</script>
<template>

  <NuxtLayout>
    <NuxtLoadingIndicator />
    <NuxtPage />
  </NuxtLayout>

</template>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;400&display=swap');

  template {
    font-family: 'Poppins', sans-serif;
  }
</style>
