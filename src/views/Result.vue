<template>
  <div class="result">
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-5">SEARCH RESULT</h1>
        <p>KeyWord: {{ $route.params.keyword }}</p>
      </v-col>
    </v-row>
    <v-row class="mb-4"></v-row>
    <v-card max-width="800" class="mx-auto">
      <v-container>
        <v-row dense>
          <v-col v-for="(item, i) in albums" :key="i" cols="12">
            <v-card color="#F5F5F5" :href="item.collectionViewUrl" target="_blank">
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title class="headline" v-text="item.collectionName"></v-card-title>

                  <v-card-subtitle v-text="item.artistName"></v-card-subtitle>
                </div>

                <v-avatar class="ma-3" size="125" tile>
                  <v-img :src="item.artworkUrl100"></v-img>
                </v-avatar>
              </div>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data: () => ({
    albums: []
  }),
  // componentが生成された時に発火する
  created () {
    axios.get(`https://itunes.apple.com/search?term=${this.$route.params.keyword}&entity=album`)
      .then(response => {
        console.log(response)
        this.albums = response.data.results
      })
  }
}
</script>
