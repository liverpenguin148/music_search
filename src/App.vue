<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <router-link to="/" style="color:white;text-decoration:none;">
          <span>MUSIC SEARCH</span>
        </router-link>
      </div>

      <v-spacer></v-spacer>

      <v-btn href="/" text>
        <span class="mr-2">Home</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
