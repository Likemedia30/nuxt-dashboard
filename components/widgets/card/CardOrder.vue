<template>
  <v-card exact nuxt to="/cabinet/order-one">
    <v-card-title class="mb-0">
      40$
    </v-card-title>
    <v-card-subtitle class="mb-0">
      translate english to dutch
    </v-card-subtitle>
    <v-sheet class="pa-3 pt-0 d-flex align-start">
      <v-avatar>
        <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="jhon">
        <span class="mark"></span>
      </v-avatar>
      <v-card-text class="pa-0 ml-2">
        Natalia Zlata
      </v-card-text>
    </v-sheet>
    <v-divider class="mx-2"></v-divider>
    <v-card-text class="d-flex justify-space-between align-center px-4 py-2">
      <div class="date font-weight-bold">
        20 feb 2021
      </div>
      <v-chip>
        completed
      </v-chip>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "card-order"
}
</script>

<style scoped>
  .v-avatar {
    position: relative;
    z-index: 1;
    overflow: visible;
  }

  .v-avatar .mark  {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background-color: green;
    position: absolute;
    bottom: 4px;
    right: 4px;
    z-index: 2;
  }
</style>