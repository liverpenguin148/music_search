<template>
  <div class="home">
    <v-container>
      <v-row class="text-center">
        <v-col class="mb-4">
          <h1 class="display-2 font-weight-bold mb-3">MUSIC SEARCH</h1>
          <p>あなたの音楽を見つけよう</p>
        </v-col>
      </v-row>
      <v-row class="text-center">
        <v-col class="col-md-10">
          <v-text-field
            v-model="keyword"
            :counter="100"
            label="アーティスト名を入力して下さい"
            aria-required
            class="text-center"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row class="text-center">
        <v-col>
          <v-btn @click="search">Search</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  data: () => ({
    keyword: ''
  }),
  methods: {
    search () {
      this.$router.push(`/result/${this.keyword}`)
    }
  }
}
</script>
