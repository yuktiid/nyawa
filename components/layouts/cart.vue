<!-- components/SidebarCart.vue -->

<template>
  <div v-if="isSidebarOpen" class="fixed inset-0 bg-black opacity-50 z-50"></div>
  <transition name="sidebar-slide">
    <div v-if="isSidebarOpen" class="fixed inset-y-0 left-0 w-64 bg-white z-50 p-4">
      <!-- Isi dari sidebar cart di sini -->
      <h2 class="text-lg font-semibold mb-4">Shopping Cart</h2>
      <!-- Tambahkan konten lainnya sesuai kebutuhan Anda -->
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      isSidebarOpen: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen;
    },
  },
};
</script>

<style scoped>

</style>
