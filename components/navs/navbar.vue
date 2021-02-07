<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      class="customBar"
      fixed
      color="primary"
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-navigation-drawer
        class="navdrawer pt-13"
        v-model="drawer"
        absolute
        left
        temporary
        light
        
      >
        <div class="close">
          <v-icon @click="drawer = false">mdi-close</v-icon>
        </div>
        <v-list
          nav
          light
        >
        <v-list-item-group
            active-class="text--accent-4"
          >
            <v-list-item-group>
              <v-list-item href="tel:+37378563423">
                  <v-list-item-icon>
                    <v-icon color="primary">mdi-phone</v-icon>
                  </v-list-item-icon>
                  <v-list-item-title>+37378563423</v-list-item-title>
              </v-list-item>
              <v-list-item href="mailto:info@likemedia.com">
                  <v-list-item-icon>
                    <v-icon color="primary">mdi-email</v-icon>
                  </v-list-item-icon>
                  <v-list-item-title color="primary">
                    info@likemedia.com
                  </v-list-item-title>
              </v-list-item>
            </v-list-item-group>
            <v-list-item-group class="d-flex justify-space-around my-7">
              <v-btn color="secondary">
                <v-icon>mdi-instagram</v-icon>
              </v-btn>
              <v-btn color="secondary" ma-0>
                <v-icon>mdi-email</v-icon>
              </v-btn>
              <v-btn color="secondary" ma-0>
                <v-icon>mdi-facebook</v-icon>
              </v-btn>
            </v-list-item-group>
            <v-list-item>
              <v-list-item-title>Acasă</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title @click="services = true">Servicii</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Despre Noi</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Experții Noștri</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Contacte</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
      <v-navigation-drawer
        class="navdrawer pt-13"
        v-model="services"
        absolute
        left
        temporary
        light
        v-on:click.native="testFunction"
      >
        <div class="close">
          <v-icon @click="closeServices">mdi-close</v-icon>
        </div>
        <v-list>
          <v-list-item>sadfasfd</v-list-item>
          <v-list-item>sadfasfd</v-list-item>
          <v-list-item>sadfasfd</v-list-item>
          <v-list-item>sadfasfd</v-list-item>
        </v-list>
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
  </v-card>
</template>

<script>
  import Listdrawer from './listdrawer.vue';

  export default {
    components: {
        Listdrawer
    },
    data: () => ({
      drawer: false,
      services: false,
      group: null
    }),
    methods: {
      closeServices() {
        this.services = false
        this.drawer = true
      },
      openServices() {
        this.services = true
        this.drawer = true
      },
      testFunction() {
        console.log("ddd")
        this.drawer = true
      }
    }
  }
</script>

<style lang="scss">
  .customBar {
    .navdrawer {
      height: 100vh !important;
      width: 100vw !important;
      max-width: 400px;
      top: 0 !important;
      left: 0 !important;
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

    a {
      text-decoration: none;
      color: inherit;
    }
  }
</style>