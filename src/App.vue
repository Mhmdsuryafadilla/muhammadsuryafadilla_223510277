<template>
  <q-layout
    view="hHh lpR fFf"
    :style="{
      backgroundImage:
        'url(src/assets/b.png)',
    }"
  >
    <!-- Navbar -->
    <q-header elevated class="bg-gradient text-white q-pa-md">
      <q-toolbar>
        <q-toolbar-title class="text-bold text-h5">
          <q-avatar>
            <img src="./assets/0.jpg">
          </q-avatar>
          Soyaa Bookshop
        </q-toolbar-title>
        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
        
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
  <q-list>

    <q-item clickable v-ripple @click="goTo('home')">
      <q-item-section avatar>
        <q-icon name="home" />
      </q-item-section>
      <q-item-section>Beranda</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('terpopuler')">
      <q-item-section avatar>
        <q-icon name="trending_up" />
      </q-item-section>
      <q-item-section>Terpopuler</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('rating')">
      <q-item-section avatar>
        <q-icon name="star" />
      </q-item-section>
      <q-item-section>Rating/Ulasan</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('cart')">
      <q-item-section avatar>
        <q-icon name="shopping_cart" />
      </q-item-section>
      <q-item-section>Keranjang</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('favorites')">
      <q-item-section avatar>
        <q-icon name="favorite" />
      </q-item-section>
      <q-item-section>Favorit</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('messages')">
      <q-item-section avatar>
        <q-icon name="message" />
      </q-item-section>
      <q-item-section>Pesan</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('feedback')">
      <q-item-section avatar>
        <q-icon name="feedback" />
      </q-item-section>
      <q-item-section>Kirim Masukan</q-item-section>
    </q-item>
    <q-item clickable v-ripple @click="goTo('help')">
      <q-item-section avatar>
        <q-icon name="help" />
      </q-item-section>
      <q-item-section>Bantuan</q-item-section>
    </q-item>
  </q-list>
</q-drawer>

    <q-page-container>
      <q-page class="q-pa-md">
        <!-- Carousel -->
        <q-carousel
          animated
          v-model="slide"
          arrows
          navigation
          infinite
          autoplay
          height="56.25vw"
          class="carousel-height q-mb-md"
        >
          <q-carousel-slide name="1" img-src="./assets/agaraku.jpg">
            <div class="q-pa-md text-center text-white bg-overlay">
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="2" img-src="./assets/layangcita.jpg">
            <div class="q-pa-md text-center text-white bg-overlay">
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="3" img-src="./assets/petualanganhati.jpg">
            <div class="q-pa-md text-center text-white bg-overlay">
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="4" img-src="./assets/rembulansenja.jpg">
            <div class="q-pa-md text-center text-white bg-overlay">
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="5" img-src="./assets/yangblmusai.jpg">
            <div class="q-pa-md text-center text-white bg-overlay">
            </div>
          </q-carousel-slide>
        </q-carousel>

        <!-- Cards Section -->
        <div class="q-gutter-md q-mt-md row justify-around">
          <q-card class="my-card">
            <q-img src="./assets/rembulansenja.jpg" />
            <q-card-section>
              <div class="text-h6 text-bold">Novel "Rembulan Senja" karya Siti Affifatul K.</div>
              <div class="text-subtitle1 text-primary">Rp.150.000</div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Beli" color="primary" @click="buyProduct('Rembulan Senja')" />
              <q-btn flat label="Tambahkan ke Keranjang" color="primary" @click="addToCart('Rembulan Senja')" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/yangblmusai.jpg" />
            <q-card-section>
              <div class="text-h6 text-bold">Novel "Yang Belum Usai"</div>
              <div class="text-subtitle1 text-primary">Rp 150.000</div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Beli" color="primary" @click="buyProduct('Yang Belum Usai')" />
              <q-btn flat label="Tambahkan ke Keranjang" color="primary" @click="addToCart('Yang Belum Usai')" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/agaraku.jpg" />
            <q-card-section>
              <div class="text-h6 text-bold">Novel "Agar Aku lebih Ikhlas" karya Wardaath</div>
              <div class="text-subtitle1 text-primary">Rp 150.000 </div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Beli" color="primary" @click="buyProduct('Agar Aku lebih Ikhlas')" />
              <q-btn flat label="Tambahkan ke Keranjang" color="primary" @click="addToCart('Agar Aku lebih Ikhlas')" />
            </q-card-actions>
          </q-card>
        </div>
      </q-page>
    </q-page-container>

    <!-- Footer -->
    <q-footer elevated class="bg-gradient-footer text-white">
      <q-toolbar>
        <q-toolbar-title>
          <div class="text-center">© 2024 Soyaa Bookshop</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const rightDrawerOpen = ref(false)
    const slide = ref(0)

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

    const viewProduct = (product) => {
      // Implementasi untuk melihat detail produk
      console.log('Lihat detail produk:', product)
    }

    const buyProduct = (product) => {
      // Implementasi untuk membeli produk
      console.log('Beli produk:', product)
    }

    const goTo = (page) => {
      // Implementasi untuk navigasi halaman
      console.log('Navigasi ke halaman:', page)
    }

    return {
      rightDrawerOpen,
      toggleRightDrawer,
      slide,
      viewProduct,
      buyProduct,
      goTo
    }
  }
}
</script>

<style>
.bg-gradient {
  background: linear-gradient(90deg, #00988f, #ff9a8b) !important;
}
.bg-gradient-footer {
  background: linear-gradient(90deg, #333, #555) !important;
}
.q-toolbar-title img {
  height: 50px;
  margin-right: 10px;
  border-radius: 50%;
}
.q-toolbar-title {
  font-family: 'Montserrat', sans-serif;
}
.q-carousel img {
  object-fit: cover;
}
.q-carousel-slide {
  transition: transform 0.8s ease;
}
.q-carousel-slide .bg-overlay {
  background: rgba(0, 0, 0, 0.4);
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.q-carousel-slide h1 {
  font-family: 'Montserrat', sans-serif;
  font-size: 2.5rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.6);
}
.q-card {
  width: 30vw;
  border: none;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background: rgba(255, 255, 255, 0.8);
}
.q-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
}
.q-card img {
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}
.q-card-section {
  padding: 16px;
}
.q-card-actions {
  padding: 16px;
}
.q-btn {
  background: linear-gradient(90deg, #00988f, #33b890) !important;
  color: white !important;
  border-radius: 8px;
  transition: background 0.3s ease;
}
.q-btn:hover {
  background: linear-gradient(90deg, #33b890, #00988f) !important;
}
.text-bold {
  font-weight: bold;
}
.text-primary {
  color: #00988f;
}
</style>
