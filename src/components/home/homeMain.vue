<template>
  <div class="main-page">
    <v-container fluid>
      <div class="search-bar-top">
        <searchBar></searchBar>
      </div>
      <div class="carousel-wrapper">
        <!-- 轮播图 -->
        <homeHeader></homeHeader>
      </div>
      <div class="four-imgs">
        <!-- 轮播图下方四个图片 -->
        <v-main class="white lighten-2">
          <v-container>
            <v-row>
              <v-col v-for="n in 4" :key="n" class="flex-wrap child-flex" cols="3">
                <v-img
                  :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                  :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                  <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
              </v-col>
            </v-row>
          </v-container>
        </v-main>
      </div>
      <div class="content-bottom-divider">
        <strong>INSTAGRAM</strong>
        <v-divider></v-divider>
      </div>
      <div class="content-bottom">
        <div class="bottom-left-imgs">
          <v-row>
            <v-col v-for="n in 9" :key="n" class="d-flex child-flex" cols="4">
              <v-img
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
                aspect-ratio="1"
                class="grey lighten-2"
              >
                <template v-slot:placeholder>
                  <v-row class="fill-height ma-0" align="center" justify="center">
                    <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                  </v-row>
                </template>
              </v-img>
            </v-col>
          </v-row>
        </div>
      </div>
      <div class="content-bottom-divider">
        <strong>more @share-lease-user</strong>
        <v-divider></v-divider>
      </div>
    </v-container>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import searchBar from '@/components/search/searchBar.vue';
import homeHeader from '@/components/home/homeHeader.vue';

export default Vue.extend<{}, {}, {}, {}>({
  name: 'home-main',
  components: { searchBar, homeHeader },

  watch: {},
});
</script>

<style>
.main-page {
}

.carousel-wrapper {
  margin-top: 7vh;
}

.content-bottom-divider {
  margin: 2vh 0;
}

.content-bottom {
  margin-top: 2vh;
  display: flex;
  /* display: flex; */
}

.content-bottom .bottom-left-imgs {
  width: 48%;
}

@media screen and (max-width: 1260px) {
  .content-bottom {
    display: block;
  }

  .content-bottom .bottom-left-imgs {
    width: 100%;
  }
}
</style>
