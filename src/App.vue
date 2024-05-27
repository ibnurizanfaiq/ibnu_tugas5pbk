<template>
  <q-layout view="hhh lpR fff">
    <q-header reveal elevated class="bg-red text-white" >
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          <q-avatar>
            <img src="./components/cc.svg" />
          </q-avatar>
          R4One Shop
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="center">
        <q-route-tab to="#page1" label="Pulsa" />
        <q-route-tab to="#page2" label="Game Online" />
        <q-route-tab to="#page3" label="Paket Data" />
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <q-item clickable v-ripple @click="leftDrawerOpen = false">
          <q-item-section>
            <q-item-label>Home</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple @click="leftDrawerOpen = false">
          <q-item-section>
            <q-item-label>Kategori</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple @click="leftDrawerOpen = false">
          <q-item-section>
            <q-item-label>Promo & Voucher</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple @click="leftDrawerOpen = false">
          <q-item-section>
            <q-item-label>Informasi</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple @click="leftDrawerOpen = false">
          <q-item-section>
            <q-item-label>Kontak</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <div id="page1">
        <div class="q-pa-md row items-start q-gutter-md">
            <q-card class="my-card bg-white text-black" v-for="card in 20" :key="card">
              <img src="./components/telkomsel.png" alt="logo telkomsel">
              <q-card-section>
                <div class="text-h6">Pulsa Telkomsel</div>
                <div class="text-subtitle2">R4One Shop</div>
              </q-card-section>
              <q-separator dark />
              <q-card-actions>
                <q-btn push color="red">AddTo Cart</q-btn>
                <q-btn push color="red">Checkout</q-btn>
              </q-card-actions>
            </q-card>
        </div>
      </div>
        
      <div id="page2">

      </div>
      <div class="q-pa-md">
        <q-carousel
          v-model="slide"
          transition-prev="slide-right"
          transition-next="slide-left"
          animated
          control-color="primary"
          class="rounded-borders"
        >
        <q-carousel-slide name="1" class="column no-wrap flex-center">
          <img src="./components/pulsa.jpg" alt="logo pulsa">
        </q-carousel-slide>
        <q-carousel-slide name="2" class="column no-wrap flex-center">
          <img src="./components/pubg.jpg" alt="logo pulsa">
        </q-carousel-slide>
        <q-carousel-slide name="3" class="column no-wrap flex-center">
          <img src="./components/ml.jpg" alt="logo pulsa">
        </q-carousel-slide>
        </q-carousel>

    <div class="row justify-center">
      <q-btn-toggle
        glossy
        v-model="slide"
        :options="[
          { label: 1, value: '1' },
          { label: 2, value: '2' },
          { label: 3, value: '3' },
        ]"
      />
    </div>
  </div>
    </q-page-container>

    <q-footer reveal elevated class="bg-red-8 text-white" align="center">
      <q-toolbar>
        <q-toolbar-title>
          R4One Shop<br>
          <p style="font-size: small;">Copyright by Ibnu 2024</p>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const leftDrawerOpen = ref(false)
    const slide = ref(0)
    const lorem = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value
    }

    return {
      leftDrawerOpen,
      slide,
      lorem,
      toggleLeftDrawer
    }
  }
}
</script>

<style>
/* Add your custom styles here */
</style>
