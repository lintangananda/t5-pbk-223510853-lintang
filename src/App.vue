<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-indigo-10 text-white">
      <q-toolbar>
        <q-btn flat round dense icon="menu" @click="toggleLeftDrawer" class="text-white" />
        <q-toolbar-title>
          <span class="text-h5">Shopper</span>
        </q-toolbar-title>

        <q-space />

        <q-btn flat label="Shipping" class="text-white" />
        <q-btn flat label="FAQ" class="text-white" />
        <q-btn flat label="Contact" class="text-white" />
        <q-btn flat round icon="shopping_cart" class="text-white" />
        <q-avatar class="q-ml-md">
          <img src="https://img.icons8.com/ios-filled/50/ffffff/user-male-circle.png" alt="user icon" />
        </q-avatar>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" side="left" bordered class="bg-black text-white">
      <q-scroll-area class="fit">
        <q-list padding class="menu-list">
          <q-item clickable v-ripple class="text-white">
            <q-item-section avatar>
              <q-icon name="directions_walk" class="text-white" />
            </q-item-section>
            <q-item-section>Men's Shoes</q-item-section>
          </q-item>
          <q-item clickable v-ripple class="text-white">
            <q-item-section avatar>
              <q-icon name="woman" class="text-white" />
            </q-item-section>
            <q-item-section>Women's Shoes</q-item-section>
          </q-item>
          <q-item clickable v-ripple class="text-white">
            <q-item-section avatar>
              <q-icon name="child_care" class="text-white" />
            </q-item-section>
            <q-item-section>Kids' Shoes</q-item-section>
          </q-item>
          <q-item clickable v-ripple class="text-white">
            <q-item-section avatar>
              <q-icon name="new_releases" class="text-white" />
            </q-item-section>
            <q-item-section>New Arrivals</q-item-section>
          </q-item>
          <q-item clickable v-ripple class="text-white">
            <q-item-section avatar>
              <q-icon name="local_offer" class="text-white" />
            </q-item-section>
            <q-item-section>On Sale</q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>



    <q-page-container>
      <q-card flat bordered class="q-pa-md bg-white">
        <q-card-section>
          <q-img src="https://www.footlocker.id/media/wysiwyg/playoffs_1600x500.jpg" class="full-width">
            <q-badge class="absolute-top-left text-caption bg-red-9 text-white">FREE SHIPPING WORLDWIDE</q-badge>
            <div class="absolute-top-right q-pa-md">
              <q-select v-model="selectedCountry" :options="countries" class="q-mr-md" emit-value map-options />
              <q-select v-model="selectedCurrency" :options="currencies" class="q-mr-md" emit-value map-options />
              <q-select v-model="selectedLanguage" :options="languages" emit-value map-options />
            </div>
          </q-img>
        </q-card-section>
      </q-card>

      <!-- Product Sections -->
      <div class="row q-my-md">
        <div class="col-4">
          <q-card flat bordered class="hover-shadow bg-indigo-1">
            <q-img src="https://sombrero.jdsports.id/pub/media/wysiwyg/ShopByCategory/Homebanner_Gender_552x823_552x823_3_1.jpg">
              <div class="absolute-bottom text-center text-h5 text-white bg-indigo-10" style="opacity: 0.7;">
                Women
              </div>
            </q-img>
            <q-card-section class="text-center">
              <q-btn flat label="Shop Women" class="text-indigo-10" />
            </q-card-section>
          </q-card>
        </div>
        <div class="col-4">
          <q-card flat bordered class="hover-shadow bg-green-1">
            <q-img src="https://sombrero.jdsports.id/pub/media/wysiwyg/ShopByCategory/Homebanner_Gender_552x823_552x823_2_1.jpg">
              <div class="absolute-bottom text-center text-h5 text-white bg-green-10" style="opacity: 0.7;">
                Men
              </div>
            </q-img>
            <q-card-section class="text-center">
              <q-btn flat label="Shop Men" class="text-green-10" />
            </q-card-section>
          </q-card>
        </div>
        <div class="col-4">
          <q-card flat bordered class="hover-shadow bg-yellow-1">
            <q-img src="https://sombrero.jdsports.id/pub/media/wysiwyg/ShopByCategory/Homebanner_Gender_552x823_552x823_1_1.jpg">
              <div class="absolute-bottom text-center text-h5 text-white bg-yellow-10" style="opacity: 0.7;">
                Kids
              </div>
            </q-img>
            <q-card-section class="text-center">
              <q-btn flat label="Shop Kids" class="text-yellow-10" />
            </q-card-section>
          </q-card>
        </div>
      </div>
    </q-page-container>


      <q-carousel
  v-model="slide"
  transition-prev="slide-right"
  transition-next="slide-left"
  swipeable
  animated
  control-color="amber"
  navigation
  padding
  arrows
  height="300px"
  class="bg-grey-1 shadow-2 rounded-borders"
  autoplay
  interval="5000"
>
  <q-carousel-slide :name="1" class="column no-wrap">
    <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
      <q-img class="rounded-borders col-6 full-height" src="https://www.footlocker.id/media/weltpixel/owlcarouselslider/images/d/e/desktop-_1600-x-500__2.png" />
      <q-img class="rounded-borders col-6 full-height" src="https://www.footlocker.id/media/weltpixel/owlcarouselslider/images/y/2/y2k_1600x500.jpg" />
    </div>
  </q-carousel-slide>
  <q-carousel-slide :name="2" class="column no-wrap">
    <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
      <q-img class="rounded-borders col-6 full-height" src="https://www.footlocker.id/media/weltpixel/owlcarouselslider/images/p/u/puma_x_nct_1600x500.jpg" />
      <q-img class="rounded-borders col-6 full-height" src="https://www.footlocker.id/media/weltpixel/owlcarouselslider/images/_/1/_1600x500_12.jpg" />
    </div>
  </q-carousel-slide>
  <q-carousel-slide :name="3" class="column no-wrap">
    <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
      <q-img class="rounded-borders col-6 full-height" src="https://www.footlocker.id/media/weltpixel/owlcarouselslider/images/h/o/hoka_clifton_2_1600x500_1.jpg" />
      <q-img class="rounded-borders col-6 full-height" src="https://storage.googleapis.com/eraspacelink/pmp/production/banners/images/vqkEh8xhnAL5TvDLWENReriuqEPYlzkgP0y0hkhV.jpg" />
    </div>
  </q-carousel-slide>
  <q-carousel-slide :name="4" class="column no-wrap">
    <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
      <q-img class="rounded-borders col-6 full-height" src="https://storage.googleapis.com/eraspacelink/pmp/production/banners/images/nzeHOMn9YR7BV7CctzYKbO9JkYN6oPnHRcSuPqSO.jpg" />
      <q-img class="rounded-borders col-6 full-height" src="https://sombrero.jdsports.id/pub/media/wysiwyg/HomeBanner2/PUMA_PALERMO_1920X840.jpg" />
    </div>
  </q-carousel-slide>
</q-carousel>

    <q-footer elevated class="bg-indigo-10 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://i.pinimg.com/474x/f9/f9/18/f9f918e7872c45d8abd9dbbba4aa07ca.jpg" />
          </q-avatar>
          <div>Lyn Shoe Store</div>
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
    const rightDrawerOpen = ref(false)
    const drawer = ref(false)
    const slide = ref(1)

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value
    }

    return {
      leftDrawerOpen,
      rightDrawerOpen,
      drawer,
      slide,
      toggleLeftDrawer
    }
  }
}
</script>

<style lang="sass" scoped>
.menu-list .q-item
  border-radius: 0 32px 32px 0
</style>
