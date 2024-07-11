<script>
import { ref } from 'vue'

export default {
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(true),
      lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
    }
  }
}
</script>

<template>
  <q-layout view="hHh lpr fFf">

    <q-header class="bg-secondary text-white" id="header" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS0lBGahvSz5qZAmW4IsThiIl14i4VI8py2Og&s">
          </q-avatar>
          Kaiju Apparel
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab href="#carousel" label="Pictures" />
        <q-route-tab href="#card" label="Get Started" />
        <q-route-tab href="#footer" label="Contact Us" />
      </q-tabs>
    </q-header>

    <div class="q-pa-md carousel" id="carousel">
      <q-carousel animated v-model="slide" navigation infinite :autoplay="autoplay" arrows transition-prev="slide-right"
        transition-next="slide-left" @mouseenter="autoplay = false" @mouseleave="autoplay = true">
        <q-carousel-slide :name="1"
          img-src="https://plus.unsplash.com/premium_photo-1700822900314-9196749b974e?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
        <q-carousel-slide :name="2"
          img-src="https://images.unsplash.com/photo-1567401893414-76b7b1e5a7a5?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
        <q-carousel-slide :name="3"
          img-src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
        <q-carousel-slide :name="4"
          img-src="https://images.unsplash.com/photo-1470309864661-68328b2cd0a5?q=80&w=1470&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
      </q-carousel>
    </div>

    <div class="q-pa-md row items-start q-gutter-md">
      <!-- <q-card class="my-card" flat bordered>
      <img src="https://cdn.quasar.dev/img/parallax2.jpg">

      <q-list>
        <q-item clickable>
          <q-item-section avatar>
            <q-icon color="primary" name="local_bar" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Bar XYZ</q-item-label>
            <q-item-label caption>Have a drink.</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable>
          <q-item-section avatar>
            <q-icon color="red" name="local_gas_station" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Gas Station</q-item-label>
            <q-item-label caption>Fill your gas tank.</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable>
          <q-item-section avatar>
            <q-icon color="amber" name="local_movies" />
          </q-item-section>

          <q-item-section>
            <q-item-label>Cinema XYZ</q-item-label>
            <q-item-label caption>Watch a movie.</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-card> -->

      <!-- <q-card class="my-card" flat bordered>
      <img src="https://cdn.quasar.dev/img/mountains.jpg">

      <q-card-actions align="right">
        <q-btn flat round color="red" icon="favorite" />
        <q-btn flat round color="teal" icon="bookmark" />
        <q-btn flat round color="primary" icon="share" />
      </q-card-actions>
    </q-card> -->

      <q-card class="my-card" id="card" flat bordered>
        <q-card-section>
          <div class="text-h6 q-mb-xs">Packet 1 : Casual</div>
          <div class="row no-wrap items-center">
            <q-rating size="18px" v-model="stars" :max="5" color="primary"></q-rating>
            <span class="text-caption text-grey q-ml-sm">4.5 (798)</span>
          </div>
        </q-card-section>

        <img
          src="https://images.unsplash.com/photo-1544441893-675973e31985?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTR8fGNhc3VhbCUyMGNsb3RoZXMlMjBwYWNrZXR8ZW58MHwwfDB8fHww">
      </q-card>
      <q-card class="my-card" flat bordered>
        <q-card-section>
          <div class="text-h6 q-mb-xs">Packet 2 : Formal</div>
          <div class="row no-wrap items-center">
            <q-rating size="18px" v-model="stars" :max="5" color="primary"></q-rating>
            <span class="text-caption text-grey q-ml-sm">4.8 (1245)</span>
          </div>
        </q-card-section>

        <img
          src="https://plus.unsplash.com/premium_photo-1676225680209-19a398a9b38a?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTN8fGZvcm1hbCUyMGNsb3RoZXMlMjBwYWNrZXR8ZW58MHwwfDB8fHww">
      </q-card>
      <q-card class="my-card" flat bordered>
        <q-card-section>
          <div class="text-h6 q-mb-xs">Sneakers or Shoes</div>
          <div class="row no-wrap items-center">
            <q-rating size="18px" v-model="stars" :max="5" color="primary"></q-rating>
            <span class="text-caption text-grey q-ml-sm">4.7 (551)</span>
          </div>
        </q-card-section>

        <img
          src="https://plus.unsplash.com/premium_photo-1682435561654-20d84cef00eb?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NXx8c25lYWtlcnN8ZW58MHwwfDB8fHww">
      </q-card>
      <q-card class="my-card" flat bordered>
        <q-card-section>
          <div class="text-h6 q-mb-xs">Jacket Variations</div>
          <div class="row no-wrap items-center">
            <q-rating size="18px" v-model="stars" :max="5" color="primary"></q-rating>
            <span class="text-caption text-grey q-ml-sm">4.6 (1551)</span>
          </div>
        </q-card-section>

        <img
          src="https://plus.unsplash.com/premium_photo-1700053641043-8cc03ce39b29?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NDl8fEphY2tldCUyMFZhcmlhdGlvbnxlbnwwfDB8MHx8fDA%3D">
      </q-card>
      <q-card class="my-card" flat bordered>
        <q-card-section>
          <div class="text-h6 q-mb-xs">Various of Accessories</div>
          <div class="row no-wrap items-center">
            <q-rating size="18px" v-model="stars" :max="5" color="primary"></q-rating>
            <span class="text-caption text-grey q-ml-sm">4.9 (3551)</span>
          </div>
        </q-card-section>

        <img
          src="https://images.unsplash.com/3/www.madebyvadim.com.jpg?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8YWNjZXNzb3JpZXN8ZW58MHwwfDB8fHww">
      </q-card>
    </div>
    <q-footer reveal elevated class="bg-grey-8 text-white" id="footer">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS0lBGahvSz5qZAmW4IsThiIl14i4VI8py2Og&s">
          </q-avatar>
          Contact Us
        </q-toolbar-title>
      </q-toolbar>

      <div class="q-pa-md">
        <q-list style="margin-left: 30px;">
          <q-item clickable tag="a" href="https://wa.me/+6285271435700" target="_blank">
            <q-item-section avatar>
              <q-icon name="fab fa-whatsapp" />
            </q-item-section>
            <q-item-section>+6285271435700</q-item-section>
          </q-item>

          <q-item clickable tag="a" href="https://www.instagram.com/mr_azri72/?hl=en" target="_blank">
            <q-item-section avatar>
              <q-icon name="fab fa-instagram" />
            </q-item-section>
            <q-item-section>@mr_azri72</q-item-section>
          </q-item>

          <q-item clickable tag="a" href="https://www.tiktok.com/@srudukdikit?_t=8nd5KI5Maq8&_r=1" target="_blank">
            <q-item-section avatar>
              <q-icon name="fab fa-tiktok" />
            </q-item-section>
            <q-item-section>@srudukdikit</q-item-section>
          </q-item>

          <q-item clickable tag="a" href="https://x.com/AzriRafli03?t=x5W1ZosWu-U1vEfe4yyVCg&s=08" target="_blank">
            <q-item-section avatar>
              <q-icon name="fab fa-twitter" />
            </q-item-section>
            <q-item-section>@AzriRafli03</q-item-section>
          </q-item>

          <q-item clickable tag="a" href="https://www.threads.net/@mr_azri72" target="_blank">
            <q-item-section avatar>
              <img src="https://www.freepnglogos.com/uploads/threads-logo-png/black-logo-threads-png-0.png" alt="Threads"
                style="width: 24px; height: 24px;">
            </q-item-section>
            <q-item-section>@mr_azri72</q-item-section>
          </q-item>
        </q-list>
        <div class="col-6" style="margin-top: 20px;">
          <iframe src="https://maps.google.com/maps?q=0%C2%B029'50.6%22N+101%C2%B028'43.6%22E&z=17&output=embed"
            width="100%" height="200" frameborder="0" style="border:0;" allowfullscreen></iframe>
        </div>
      </div>
    </q-footer>
  </q-layout>
</template>

<style scoped>
.my-card {
  width: 100%;
  max-width: 250px;
}

#footer {
  position: static;
  bottom: 0;
  width: 100%;
  margin-top: 50px;
}

#header {
  position: sticky;
  bottom: 0;
  margin: 0;
  z-index: 4;
}

.carousel {
  margin-bottom: 50px;
}
</style>