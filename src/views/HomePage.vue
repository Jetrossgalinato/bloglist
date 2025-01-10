<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          slim
          @click="onClick"
          rounded="xl"
          elevation="6"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-card-title
            class="text-h5 text-md-h5 text-lg-h4 font-weight-bold text-center d-flex align-center justify-center mt-16 mb-5"
          >
            Welcome to Bloglist
            <span class="mdi mdi-incognito mr-2"></span>
          </v-card-title>
          <v-card-subtitle class="text-center">
            A place to share your thoughts with the world anonymously
          </v-card-subtitle>
          <v-card :class="cardClass" class="mx-auto card" elevation="16" max-width="750">
            <v-card-item>
              <v-card-title class="font-weight-bold"> Blogs </v-card-title>

              <v-card-subtitle>these are the recent posted blogs</v-card-subtitle>
            </v-card-item>

            <v-card-text>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
              incididunt ut labore et dolore magna aliqua.
            </v-card-text>
          </v-card>
        </v-container>
      </v-main>
    </v-app>
  </v-responsive>
</template>

<script setup>
import { computed, ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}

const cardClass = computed(() => ({
  'bg-white': theme.value === 'light',
  'bg-dark': theme.value === 'dark',
}))
</script>

<style>
.bg-white {
  background-color: white;
  color: black; /* Ensures text is readable in light mode */
}
.bg-dark {
  background-color: #121212; /* Dark mode background */
  color: white; /* Ensures text is readable in dark mode */
}
.card {
  margin-top: 10%;
  border-radius: 10px;
  border: 2px solid #ccc;
  padding: 3%;
}
</style>
