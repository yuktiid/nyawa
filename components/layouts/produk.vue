<template>
  <div>
    <ProductPopup
      v-if="isPopupVisible"
      :selectedProduct="selectedProduct"
      :closePopup="closePopup"
    />
    <div class="grid grid-cols-2 md:grid-cols-4 gap-y-20 gap-x-5 md:gap-x-9 m-3 md:m-9 mb-28 pb-12 z-0">
      <div v-for="(product, index) in products" :key="index" class="relative group">
        <img
          :src="hoveredIndex === index ? product.hoveredImage : product.image"
          :alt="product.name"
          class="w-full h-full object-cover cursor-pointer rounded"
          @mouseover="handleImageHover(index)"
          @mouseout="handleImageHover(-1)"
        />
        <div class="absolute top-0 left-0 p-2 opacity-0 group-hover:opacity-100 transition-opacity">
          <button @click="showProductDetail(product)" class="bg-gray-800 text-white p-2 rounded">&#x002B;</button>
        </div>
        <div class="p-2 text-center">
          <h3 class="text-sm md:text-lg font-semibold">{{ product.name }}</h3>
          <p class="text-sm md:text-md text-gray-600">{{ product.price }}</p>
        </div>

      </div>
    </div>
  </div>
</template>


<script>
import ProductPopup from '~/components/layouts/popup.vue';

export default {
  components: {
    ProductPopup,
  },
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleImageHover(index) {
      // Implement logic to change image on hover
      // You can use a data property to keep track of the hovered index
    },
    showProductDetail(product) {
      // Implement logic to show product details in a popup
      // You can use a modal or a custom popup component
    },
  },
   data() {
    return {
      hoveredIndex: -1,
      isPopupVisible: false,
      selectedImageIndex: 0,
    };
    
  },
  methods: {
    handleImageHover(index) {
      this.hoveredIndex = index;
    },
    showProductDetail(product) {
      this.isPopupVisible = true;
      this.selectedProduct = product;
    },
    closePopup() {
      this.isPopupVisible = false;
      this.selectedProduct = null;
      
    },
  },
};
</script>

<style scoped>
/* Add your custom styles here if needed */
</style>
