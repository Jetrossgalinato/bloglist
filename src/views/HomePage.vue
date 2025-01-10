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
          <h1>Welcome to Bloglist</h1>
        </v-container>
      </v-main>
    </v-app>
  </v-responsive>
</template>

<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<style>
h1 {
  margin-top: 10%;
  text-align: center;
}
</style>
