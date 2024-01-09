<template>
  <div>
    <ProductList :products="products" />
  </div>
</template>

<script>
import ProductList from '~/components/layouts/produk.vue';

export default {
  components: {
    ProductList,
  },

  data() {
    return {
      products: [
      {
            id: 1,
            name: 'Shenelin Celana Panjang Highwaist Flare Cutbray Jeans',
            price: 'Rp 339.000',
            image: 'https://down-id.img.susercontent.com/file/sg-11134201-7rblh-lnfxbo5xf5wsb9',
            hoveredImage: 'https://down-id.img.susercontent.com/file/sg-11134201-7rbkn-lnfxbnrhyvm2c4',
            images: ['https://down-id.img.susercontent.com/file/sg-11134201-7rbkn-lnfxbnrhyvm2c4', 'https://down-id.img.susercontent.com/file/sg-11134201-7rbmz-lnfxbnw7rzcg4c', 'https://down-id.img.susercontent.com/file/sg-11134201-7rbm0-lnfxbofwz5qf81', 'https://down-id.img.susercontent.com/file/sg-11134201-7rbkd-lnfxbom0q7jgb8', 'https://down-id.img.susercontent.com/file/sg-11134201-7rblh-lnfxbo5xf5wsb9'],
            color: 'black',
            sizes: ['XS', 'S', 'M', 'L', 'XL'],
            stock: {
              XS: 10,
              S: 15,
              M: 20,
              L: 12,
              XL: 0,
            },
            selectedSize: null,
            selectedImageIndex: 0,
            description: `
            <p>Kepuasan customer adalah prioritas utama kami. Cuma Shenelin yang memberikan GARANSI KEPUASAN di Indonesia!<br> Jika produk yang kamu terima tidak pas, tidak sesuai, tidak suka, mohon untuk menghubungi customer care Shenelin. Kamu mendapatkan garansi boleh menukar produk yang kamu beli dengan size / warna /  produk lain.</p>
            <p><strong>T&C Exchange:</strong></p>
            <p>- Penukaran wajib info ke Customer service</p>
            <p>- Batas penukaran 7 hari setelah barang diterima</p>
            <p>- Mengisi kartu garansi</p>
            <p>- Produk belum dicuci, dipakai seharian, atau dipermak.</p>
            <p>- Label hangtag masih terpasang.</p>
            <p>- Untuk penukaran harus dengan barang/harga yang sama atau lebih tinggi, kami tidak menerima proses refund selisih harga.</p>
            `,
            showDescription: false,
          },
        {
          name: 'Gyuzi Shirt / Top',
          price: 'Rp 589.900',
          image: 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/791b63dd-25c5-4ad0-a926-413b1e05c982.jpg',
          hoveredImage: 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/bb58975b-ad1d-4fad-a83d-014714de8b30.jpg',
          images: ['https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/bb58975b-ad1d-4fad-a83d-014714de8b30.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/791b63dd-25c5-4ad0-a926-413b1e05c982.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/7547b086-7e00-41f4-b302-4cf0ab30d1c7.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/6045e183-381f-45dc-bd75-00ebb216c2d4.jpg', 'https://images.tokopedia.net/img/cache/900/VqbcmM/2023/9/18/078d3e45-271d-4a97-8679-4273c9c8943d.jpg'],
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
            <p>Brand : NYAWA</p>
            <p>Material/bahan : Tencel (Organic)</p>
            <p>Size available : M,L,XL</p>
            <br>
            <p>Custom size available by pre-order</p>
            <br>
            <p>Instagram : @_nyawa__</p>
            <p>Tiktok : nyawaofficial</p>
            <p>Offline store : Paripolla at 23 Paskal Mall Bandung</p>
            `,
            showDescription: false,
        },
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
        },
      ],
      hoveredIndex: -1,
      isPopupVisible: false,
      selectedProduct: null,
    };
  },
  methods: {
  // ...
  selectProduct(product) {
    this.selectedProduct = product;
    this.isPopupVisible = true;
    }, 
  },
  mounted() {
    // Pilih ukuran paling kecil yang stoknya kurang dari atau sama dengan 0 saat data dimuat
    this.products.forEach(product => {
      const availableSizes = product.sizes.filter(size => product.stock[size] > 0);
      if (availableSizes.length > 0) {
        const smallestAvailableSize = availableSizes.reduce((minSize, size) => {
          return product.stock[size] < product.stock[minSize] ? size : minSize;
        }, availableSizes[0]);

        // Menetapkan ukuran terpilih jika belum ada yang dipilih
        if (!product.selectedSize) {
          product.selectedSize = smallestAvailableSize;
        }
      }
    });
  },
};
</script>

