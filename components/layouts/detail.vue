<template>
    <div class="container mx-auto p-4">
      <div v-for="product in products" :key="product.id" class="grid md:flex items-start justify-between ">
        <div class="grid grid-flow-col md:grid-flow-row md:grid-cols-1 gap-4 mt-5 order-2 md:order-1">
          <img
            v-for="(image, index) in product.images"
            :src="image"
            :alt="`${product.name} - Image ${index + 1}`"
            @click="selectImage(product, index)"
            :key="index"
            class="w-24 h-auto cursor-pointer rounded"
          />
        </div>

        <div class="flex-shrink-0 w-full md:w-2/6 md:mx-9 order-1 md:order-2">
          <img :src="product.image" :alt="product.name" @mouseover="hoverImage(product)" class="w-full h-auto rounded">
        </div>

        <div class="flex-grow md:w-1/3 mt-5 order-3 md:order-3">
        <p class="text-md font-bold mb-4">NYAWA</p>
          <p class="text-2xl font-medium mb-4">{{ product.name }}</p>
          <p class="text-gray-600 text-xl mb-4">{{ product.price }}</p>
        <hr>
            <div class="my-6">
                <button @click="toggleDescription(product)" class="text-blue-500 underline cursor-pointer">
                {{ product.showDescription ? 'Sebunyikan Deskripsi' : 'Deskripsi Produk' }}
                </button>
                <div v-if="product.showDescription" class="mt-2">
                    <div v-html="product.description"></div>
                </div>
            </div>
        <hr>
            <p class="text-gray-600 my-2">Color: {{ product.color }}</p>

            <p class="text-gray-600 mb-2">Size:</p>
            <!-- Tambahan informasi produk lainnya -->
            <!-- Tambahan informasi produk lainnya -->
            <div class="flex items-center space-x-1">
                <template v-for="(size, index) in product.sizes" :key="index">
                    <input
                        type="radio"
                        :id="`size-${index}`"
                        :value="size"
                        v-model="product.selectedSize"
                        class="hidden"
                    />
                    <label
                        :for="`size-${index}`"
                        :class="{ 'text-red-500 text-center': product.stock[size] === 0 }"
                        :style="{ 'border': product.selectedSize === size ? '2px solid #000000' : '2px solid #e2e8f0' }"
                        class="cursor-pointer inline-block px-4 py-2 border rounded transition duration-300
                            hover:bg-slate-100 focus:outline-none text-center"
                    >
                        {{ size }}
                    </label>
                </template>
            </div>

            <!-- stok -->
            <div class="mb-2">
                <span v-if="product.stock[product.selectedSize] > 0" class="text-xs">
                    Stok: {{ product.stock[product.selectedSize] }} tersedia
                </span>
                <span v-else class="text-xs text-red-500">Stok habis</span>
            </div>

        <!-- Tombol aksi -->
            <div v-if="product.selectedSize">
                <div class="md:flex justify-items-center ">
                <button
                    v-if="product.stock[product.selectedSize] > 0"
                    @click="addToCart"
                    class="my-2  md:m-4 bg-transparent text-black px-4 py-2 rounded block w-full md:basis-1/2 border transition duration-300 hover:bg-black hover:text-white"
                >
                    Tambah ke Keranjang
                </button>
                <button
                    v-if="product.stock[product.selectedSize] > 0"
                    @click="buyNow"
                    class="my-2  md:m-4 bg-black text-white px-4 py-2 rounded block w-full md:basis-1/2 border transition duration-300 hover:bg-white hover:text-black"
                >
                    Beli Sekarang
                </button>

                <button
                    v-else
                    class="my-2  md:m-4 bg-gray-400 text-white px-4 py-2 rounded cursor-not-allowed block w-full"
                    disabled
                >
                    Stok Habis
                </button>
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
        products: [
            {
            name: 'Patrick Pullover Jacket Abstract',
            price: 'Rp 775.900',
            image: 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/6a6b6df9-d7b6-455e-8953-5f21b5ac9297.jpg',
            hoveredImage: 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/dcae668f-56ef-49fc-9da7-bf02e420cd11.jpg',
            images: ['https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/6a6b6df9-d7b6-455e-8953-5f21b5ac9297.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/dcae668f-56ef-49fc-9da7-bf02e420cd11.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/cad57176-2cba-42c3-a115-93d770dbb235.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/b02d561e-e767-43cb-867c-5b46d71627c6.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/9e29343f-2449-4427-8471-82981e99496a.jpg'],
            color: 'black',
            sizes: ['XS', 'S', 'M', 'L', 'XL'],
            stock: {
            XS: 0,
            S: 0,
            M: 2,
            L: 3,
            XL: 4,
            selectedSize: null,
            },
            selectedSize: null,
                selectedImageIndex: 0,
                description: `
                <p>Kondisi: Baru</p>
                <p>Min. Pemesanan: 1 Buah</p>
                <p>Brand : NYAWA</p>
                <p>Material/bahan : Cotton,Lurik</p>
                <p>Size available : M,L,XL</p>
                <br>
                <p>Custom size available by pre-order</p>
                <br>
                <p>Instagram : @_nyawa__</p>
                <p>Tiktok : nyawaofficial</p>
                <p>Offline store : Paripolla at 23 Paskal Mall Bandung</p>
                `,
                showDescription: false,
            }
        ],
      };
    },
    methods: {
      selectImage(product, index) {
        product.image = product.images[index];
        product.selectedImageIndex = index;
      },
      toggleDescription(product) {
      product.showDescription = !product.showDescription;
        },
    },
  };
  </script>
  