<template>
  <div class="fixed inset-0 bg-black bg-opacity-50 flex items-end md:items-center justify-center z-10">
    
    <div class="bg-white p-5 w-full md:w-auto h-5/6 md:h-5/6 rounded overflow-auto">
    <button @click="closePopup" class="justify-self-end bg-none text-black px-4 py-2 rounded">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
    </button>
      <div class="flex flex-col md:flex-row">
        <!-- Bagian Kiri: Gambar Produk -->
        <div class="flex-shrink-0 mr-4 mb-4 md:mb-0">          
          <!-- Gambar Utama Produk -->
            <img :src="selectedProduct.images[selectedProduct.selectedImageIndex]" :alt="selectedProduct.name" class="w-full md:w-96 h-auto object-cover rounded" />
            <div class="flex items-center mt-4">
                <template v-for="(image, imageIndex) in selectedProduct.images" :key="imageIndex">
                    <img
                        :src="image"
                        :alt="selectedProduct.name"
                        @click="selectImage(imageIndex)"
                        @mouseover="handleHoveredImage(imageIndex)"
                        @mouseout="handleHoveredImage(null)"
                        class="w-12 h-12 object-cover rounded cursor-pointer mr-2 border hover:border-gray-500"
                    />
                </template>
                </div>
            </div>
        <!-- Bagian Kanan: Informasi Produk -->
        <div class="p-4 md:p-9 flex-grow">
            <img src="/logo1.png" alt="Logo" class="h-8 w-auto mb-3" />
            <h2 class="text-xl font-semibold mb-2">{{ selectedProduct.name }}</h2>
            <p class="text-gray-600 mb-2 text-lg tracking-wider">{{ selectedProduct.price }}</p>
            <p class="capitalize my-3">color : {{ selectedProduct.color }}</p>
            <p class="mb-2">Size:</p>
            <!-- Tambahan informasi produk lainnya -->
            <div class="flex items-center space-x-1">
                <template v-for="(size, index) in selectedProduct.sizes" :key="index">
                    <input
                        type="radio"
                        :id="`size-${index}`"
                        :value="size"
                        v-model="selectedProduct.selectedSize"
                        class="hidden"
                    />
                    <label
                        :for="`size-${index}`"
                        :class="{ 'text-red-500 text-center': selectedProduct.stock[size] === 0 }"
                        :style="{ 'border': selectedProduct.selectedSize === size ? '2px solid #000000' : '2px solid #e2e8f0' }"
                        class="cursor-pointer inline-block px-4 py-2 border rounded transition duration-300
                            hover:bg-slate-100 focus:outline-none text-center"
                    >
                        {{ size }}
                    </label>
                    
                </template>
            </div>
            <!-- stok -->
            <div class="mb-2">
            <span v-if="selectedProduct.stock[selectedProduct.selectedSize] > 0" class="text-xs">
                Stok: {{ selectedProduct.stock[selectedProduct.selectedSize] }} tersedia
            </span>
            <span v-else class="text-xs text-red-500">Stok habis</span>
            </div>
        <!-- Tombol aksi -->
            <div v-if="selectedProduct.selectedSize">
                <button
                v-if="selectedProduct.stock[selectedProduct.selectedSize] > 0"
                @click="addToCart"
                class="m-4 bg-green-500 text-white px-4 py-2 rounded block w-full"
                >
                Tambah ke Keranjang
                </button>
                <button
                v-if="selectedProduct.stock[selectedProduct.selectedSize] > 0"
                @click="buyNow"
                class="m-4 bg-yellow-500 text-white px-4 py-2 rounded block w-full"
                >
                Beli Sekarang
                </button>
                <button
                v-else
                class="m-4 bg-gray-400 text-white px-4 py-2 rounded cursor-not-allowed block w-full"
                disabled
                >
                Stok Habis
                </button>
                <nuxt-link class="hover:text-red-500 text-black px-4 block underline underline-offset-4" :to="{ name:'detail-produk' }">Detail Produk</nuxt-link>
            </div>
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
data() {
  return {
    hoveredImageIndex: null,
    // ... (data lainnya)
  };
},
mounted() {
    // Set selectedImageIndex ke 0 jika belum ada yang dipilih
    if (this.selectedProduct.selectedImageIndex === null || this.selectedProduct.selectedImageIndex === undefined) {
      this.selectedProduct.selectedImageIndex = 0;
    }
},
  props: {
    selectedProduct: {
      type: Object,
      required: true,
    },
    closePopup: {
      type: Function,
      required: true,
    },
  },
  methods: {
    addToCart() {
    if (this.selectedProduct.selectedSize) {
        // Implementasi penambahan ke keranjang sesuai dengan ukuran yang dipilih
        // Gunakan this.selectedProduct.selectedSize dan this.selectedProduct untuk mendapatkan informasi yang diperlukan
        console.log(`Menambahkan ${this.selectedProduct.name} (${this.selectedProduct.selectedSize}) ke keranjang.`);
    } else {
        console.log('Pilih ukuran terlebih dahulu.');
    }
    },

    buyNow() {
    if (this.selectedProduct.selectedSize) {
        // Implementasi penambahan ke keranjang sesuai dengan ukuran yang dipilih
        // Gunakan this.selectedProduct.selectedSize dan this.selectedProduct untuk mendapatkan informasi yang diperlukan
        console.log(`Menambahkan ${this.selectedProduct.name} (${this.selectedProduct.selectedSize}) ke keranjang.`);
    } else {
        console.log('Pilih ukuran terlebih dahulu.');
    }
    },

    selectImage(index) {
        this.selectedProduct.selectedImageIndex = index;
        this.hoveredImageIndex = null;
    },
    handleHoveredImage(index) {
        this.hoveredImageIndex = index;
    },
    
  },
};
</script>

<style scoped>
/* Tambahkan gaya sesuai kebutuhan */
</style>
