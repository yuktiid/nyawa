<template>
  <div>
    <div class="flex">
      <div class="w-1/4">
        <div v-for="(product, index) in products" :key="index" @click="selectProduct(index)">
          <img :src="product.thumbnail" alt="Product Thumbnail" class="w-16 h-16 mb-2 cursor-pointer">
        </div>
      </div>
      <div class="w-3/4">
        <div>
          <img :src="selectedProduct.image" alt="Selected Product" class="w-full h-auto" @click="toggleImageModal">
        </div>
        <div>
          <h2 class="text-xl font-bold mt-4">{{ selectedProduct.name }}</h2>
          <p class="text-gray-600">{{ selectedProduct.description }}</p>
          <!-- Add other product details as needed -->
        </div>
      </div>
    </div>

    <!-- Image Modal -->
    <div v-if="isImageModalOpen" class="fixed inset-0 bg-black bg-opacity-75 flex items-center justify-center">
      <img :src="selectedProduct.image" alt="Selected Product" class="max-w-full max-h-full" @click="toggleImageModal">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { name: "Product 1", thumbnail: "/path/to/thumbnail1.jpg", image: "/path/to/image1.jpg", description: "Description 1" },
        { name: "Product 2", thumbnail: "/path/to/thumbnail2.jpg", image: "/path/to/image2.jpg", description: "Description 2" },
        // Add more products as needed
      ],
      selectedProduct: {},
      isImageModalOpen: false,
    };
  },
  methods: {
    selectProduct(index) {
      this.selectedProduct = this.products[index];
    },
    toggleImageModal() {
      this.isImageModalOpen = !this.isImageModalOpen;
    },
  },
};
</script>
