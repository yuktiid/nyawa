<template>
  <nav class="p-2 lg:p-4 border-b">
    <div class="container mx-auto flex items-center justify-between text-transform: capitalize">
      <div class="flex-initial w-32">
        <ul class="flex space-x-4">
          <li class="hidden lg:block">
            <nuxt-link class="hover:text-red-500 text-black" :to="{ name:'belanja' }">belanja</nuxt-link>
          </li>
          <li class="hidden lg:block">
            <nuxt-link class="hover:text-red-500 text-black" :to="{ name:'promo' }">promo</nuxt-link>
          </li>
          <li class="hidden lg:block">
            <nuxt-link class="hover:text-red-500 text-black" :to="{ name:'inspirasi' }">inspirasi</nuxt-link>
          </li>
          <li class="hidden lg:block">
            <nuxt-link class="hover:text-red-500 text-black" :to="{ name:'blog' }">blog</nuxt-link>
          </li>
        <!-- Tambahkan class 'hidden' jika layar cukup kecil -->
          <li class=" md:hidden">
              <button @click="toggleMenu">
                <!-- Icon hamburger -->
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
                </svg>
              </button>
          </li>

        </ul>
      </div>
      <!--  -->
      <div class="flex-initial w-64">
        <nuxt-link to="/" class="">
          <NuxtImg src="/logo1.png" alt="Logo" class="mx-auto h-14 lg:h-20 w-auto" />
        </nuxt-link>
      </div>
      <!--  -->
      <div class="flex-initial w-32">
        <ul class="flex space-x-4">
          <!-- Tambahkan class 'hidden' jika layar kecil -->
          <li class="hidden lg:block">
            <nuxt-link to="login" class="hover:text-red-500 text-black">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round"
                  d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"></path>
              </svg>
            </nuxt-link>
          </li>
          <li class="">
            <nuxt-link to="#" class="hover:text-red-500 text-black">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round"
                  d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"></path>
              </svg>
            </nuxt-link>
          </li>
          <li class="">
            <button @click="toggleCart" type="button" class="relative -m-2 p-2 text-black hover:text-gray-500">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round"
                  d="M15.75 10.5V6a3.75 3.75 0 10-7.5 0v4.5m11.356-1.993l1.263 12c.07.665-.45 1.243-1.119 1.243H4.25a1.125 1.125 0 01-1.12-1.243l1.264-12A1.125 1.125 0 015.513 7.5h12.974c.576 0 1.059.435 1.119 1.007zM8.625 10.5a.375.375 0 11-.75 0 .375.375 0 01.75 0zm7.5 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z">
                </path>
              </svg>
            </button>
          </li>
        </ul>
      </div>
      <!--  -->
    </div>
  </nav>

 <!-- Offcanvas Menu -->
    <transition name="fade">
      <div v-if="isMenuOpen" class="fixed inset-0 bg-gray-800 bg-opacity-75 z-50" @click="closeMenu"></div>
    </transition>
    <transition name="slide">
      <div v-if="isMenuOpen" class="fixed inset-y-0 left-0 max-w-xs w-full bg-white shadow-md overflow-y-auto z-50 pt-7 capitalize">
        <!-- ... Isi menu offcanvas ... -->
        <button @click="closeMenu" class="px-4">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
        <ul class="py-4">
          <li class="flex justify-around">
              <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name: 'login' }">Login</nuxt-link>
              <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name: 'register' }">Register</nuxt-link>
          </li>
          <li class="ps-10 relative group">
            <div class="flex items-center">
              <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" @click="toggleDropdown('belanja')">
                Belanja
                <span v-if="activeDropdown === 'belanja'" class="ml-2">&#x2212;</span>
                <span v-else class="ml-2">+</span>
              </nuxt-link>
            </div>
            <div v-if="activeDropdown === 'belanja'" class="dropdown-menu">
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'belanja' }">koleksi</nuxt-link>
              </li>
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'belanja' }">pria</nuxt-link>
              </li>
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'belanja' }">wanita</nuxt-link>
              </li>
            </div>
          </li>
          <li class="ps-10 relative group">
            <div class="flex items-center">
              <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" @click="toggleDropdown('promo')">
                promo
                <span v-if="activeDropdown === 'promo'" class="ml-2">&#x2212;</span>
                <span v-else class="ml-2">&#x002B;</span>
              </nuxt-link>
            </div>
            <div v-if="activeDropdown === 'promo'" class="dropdown-menu">
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'promo' }">koleksi natal 2023</nuxt-link>
              </li>
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'promo' }">koleksi desainer</nuxt-link>
              </li>
              <li class="ps-10">
                <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'promo' }">musim gugur / dingin 2023</nuxt-link>
              </li>
            </div>
          </li>
          <li class="ps-10">
            <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'inspirasi' }">inspirasi</nuxt-link>
          </li>
          <li class="ps-10">
            <nuxt-link class="block px-4 py-2 text-gray-800 hover:bg-gray-200" :to="{ name:'blog' }">blog</nuxt-link>
          </li>
          
        </ul>
      </div>
    </transition>
    <!--  -->

    <transition name="sidebar-slide">
      <div v-if="cartmenu" class="fixed inset-y-0 right-0 w-80 bg-white z-50 p-4">
        <div class="grid grid-cols-2 content-center">
          <button @click="closecart" class="">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
          <h2 class="text-lg font-semibold">Shopping Cart</h2>
        </div>
          <div>
            <!-- barang -->
            <div class="my-8">
              <div class="flow-root">
                <ul role="list" class="-my-6 divide-y divide-gray-200">
                  <li v-for="(product, index) in products" :key="index" class="flex py-6">
                    <div class="h-24 w-24 flex-shrink-0 overflow-hidden rounded-md border border-gray-200">
                      <img :src="product.image" :alt="product.name" class="h-full w-full object-cover object-center">
                    </div>

                    <div class="ml-4 flex flex-1 flex-col">
                      <div>
                        <div class="flex justify-between text-base font-medium text-gray-900">
                          <h3>
                            <a :href="product.link">{{ product.name }}</a>
                          </h3>
                          <p class="ml-4">{{ product.price }}</p>
                        </div>
                        <p class="mt-1 text-sm text-gray-500">{{ product.color }}</p>
                      </div>
                      <div class="flex flex-1 items-end justify-between text-sm">
                        <p class="text-gray-500">{{ product.quantity }}</p>

                        <div class="flex">
                          <button type="button" class="font-medium text-indigo-600 hover:text-indigo-500" @click="removeProduct(index)">Remove</button>
                        </div>
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </div>

            <!-- total -->
            <div class="border-t border-gray-200 px-4 py-6 sm:px-6">
              <div class="flex justify-between text-base font-medium text-gray-900">
                <p>Total</p>
                <p>{{ calculateSubtotal() }}</p>
              </div>
              <p class="mt-0.5 text-sm text-gray-500">pengiriman dan pajak saat Checkout</p>
              <div class="mt-6">
                <nuxt-link to="#" class="flex items-center justify-center rounded-md border border-transparent bg-indigo-600 px-6 py-3 text-base font-medium text-white shadow-sm hover:bg-indigo-700">Checkout</nuxt-link>
              </div>
              <div class="mt-6 flex justify-center text-center text-sm text-gray-500">
                <p>
                  atau
                  <button type="button" class="font-medium text-indigo-600 hover:text-indigo-500">
                    Lanjutkan Belanja
                    <span aria-hidden="true"> &rarr;</span>
                  </button>
                </p>
              </div>
            </div>
          </div>
      </div>
    </transition>

</template>

<script>

export default {
  data() {
    return {
      isMenuOpen: false,
      cartmenu: false,
      activeDropdown: null,
      products: [
        {
          name: "kaos",
          image: "img6.jpeg",
          link: "#",
          price: "Rp.300.000",
          color: "navy",
          quantity: "Qty 1",
        },
        {
          name: "Bali",
          image: "img7.jpeg",
          link: "#",
          price: "Rp.350.000",
          color: "offwhite",
          quantity: "Qty 1",
        },
        // Add more products as needed
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
    toggleCart() {
      this.cartmenu = !this.cartmenu;
    },
    closecart() {
      this.cartmenu = false;
    },
    toggleDropdown(name) {
      if (this.activeDropdown === name) {
        this.activeDropdown = null;
      } else {
        this.activeDropdown = name;
      }
    },
    removeProduct(index) {
      this.products.splice(index, 1);
    },
calculateSubtotal() {
      // Hitung subtotal berdasarkan produk di keranjang
      const subtotal = this.products.reduce((total, product) => {
        // Hapus "Rp" dan koma, lalu konversi menjadi angka
        const price = parseFloat(product.price.replace(/[^0-9,-]/g, "").replace(",", "."));

        return total + price;
      }, 0);

      // Format sebagai Rupiah
      return `Rp${subtotal.toLocaleString("id-ID")}`;
    },
  },
};
</script>

<style scoped>
/* Transisi fade */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
.fade-enter-to, .fade-leave {
  opacity: 1;
}

/* Transisi slide */
.slide-enter-active, .slide-leave-active {
  transition: transform 0.5s;
}
.slide-enter, .slide-leave-to {
  transform: translateX(-100%);
}
.slide-enter-to, .slide-leave {
  transform: translateX(0);
}
/*  */
.sidebar-slide-enter-active, .sidebar-slide-leave-active {
  transition: transform 0.5s;
}
.sidebar-slide-enter, .sidebar-slide-leave-to {
  transform: translateX(100%);
}
.sidebar-slide-enter-to, .sidebar-slide-leave {
  transform: translateX(0);
}
/*  */

</style>

