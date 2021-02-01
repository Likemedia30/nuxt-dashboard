<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      class="customBar"
      absolute
      color="white"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-navigation-drawer
        class="navdrawer"
        v-model="drawer"
        absolute
        left
        temporary
      >
        <div class="close">
          <v-icon @click="drawer = false">mdi-close</v-icon>
        </div>
        <listdrawer></listdrawer>
      </v-navigation-drawer>
      
      <v-spacer></v-spacer>
      <v-toolbar-title>
        <img class="logo" src="@/static/logo.svg" alt="">
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon dark>mdi-account</v-icon>
      </v-btn>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-7"
      class="overflow-y-auto"
      max-height="600"
    >
    </v-sheet>
  </v-card>
</template>

<script>
  import listdrawer from '@/components/navs/listdrawer';
import Listdrawer from './listdrawer.vue';

  export default {
    components: {
        Listdrawer
    },
    data: () => ({
      drawer: false,
      group: null
    }),
    watch: {
      group () {
        this.drawer = false
      },
    },
  }
</script>

<style lang="scss" scoped>
  .customBar {
    background: $custom_blue !important;

    .navdrawer {
      height: 100vh !important;
      width: 100vw !important;
      max-width: 400px;
    }

    .logo {
      width: 120px;
      height: 40px;
      margin-top: 10px;
    }

    .close {
      position: absolute;
      right: 20px;
      top: 20px;
      z-index: 1;
    }
  }
</style>