<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      class="customBar"
      fixed
      color="primary"
      elevate-on-scroll
      dark
    >
      <v-app-bar-nav-icon @click.stop="drawer = true"></v-app-bar-nav-icon>

      <v-navigation-drawer
        class="navdrawer pt-13"
        v-model="drawer"
        absolute
        left
        temporary
        light
        stateless
        max-height="100vh"
      >
        <div class="close">
          <v-icon @click="drawer = false">mdi-close</v-icon>
        </div>
        <contacts></contacts>
        <v-list
          nav
          light
        >
          <v-list-item-group>
            <v-list-item v-for="(item, i) in drawerItems" :key="i" nuxt :to="item.href">

              <v-list-item-title v-if="item.action" v-text="item.title" @click.stop="openServices"></v-list-item-title>
              <v-list-item-title v-else v-text="item.title"></v-list-item-title>
              <v-list-item-icon>
                <v-icon v-text="item.icon"></v-icon>
              </v-list-item-icon>
            </v-list-item>
          </v-list-item-group>
        </v-list>
        <template v-slot:append>
          <div class="pa-2 mb-4">
            <v-btn color="secondary" outlined block>
              Cabinet
            </v-btn>
          </div>
        </template>
      </v-navigation-drawer>
      <v-navigation-drawer
        class="navdrawer pt-13"
        v-model="services"
        absolute
        left
        temporary
        light
        stateless
      >
        <div class="close">
          <v-icon @click="closeServices">mdi-arrow-left-circle</v-icon>
        </div>
        <v-list nav light>
          <v-list-item-group>
            <v-list-item v-for="service in servicesItems" :key="service.identifier" @click.stop="openSubservices(service.identifier)">
              <v-list-item-title v-text="service.title"></v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
      <v-navigation-drawer
        class="navdrawer pt-13"
        v-model="subservices"
        absolute
        left
        temporary
        light
      >
        <div class="close">
          <v-icon @click="closeSubservices">mdi-arrow-left-circle</v-icon>
        </div>
        <v-list nav light>
          <v-list-item-group>
            <v-list-item v-for="(service, i) in subserviceIdentifier" :key="i">
              <v-list-item-title v-text="service"></v-list-item-title>
            </v-list-item>
          </v-list-item-group>
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
  import Contacts from './contacts';

  export default {
    components: {
        Contacts
    },
    data: () => ({
      drawer: false,
      services: false,
      subservices: false,
      subserviceIdentifier: [ ],
      group: null,
      drawerItems: [
        {
          title: "Acasă",
          icon: "",
          action: null,
          href: '/'
        },
        {
          title: "Servicii",
          icon: "mdi-arrow-right-drop-circle-outline",
          action: true
        },
        {
          title: "Despre Noi",
          icon: "",
          action: null,
          href: "/about"
        },
        {
          title: "Experții Noștri",
          icon: "",
          action: null,
          href: "/experts"
        }
      ],
      servicesItems: [
        {
          
          title: "Cetățenie Română",
          identifier: "cetro",
          subservices: [
            "Depunerea actelor pentru redobândirea cetățeniei",
            "Depunerea Jurămîntului",
            "Obținerea CI",
            "Obținerea Pașaport Străin Ro",
            "Alocații pentru copiii cu cetățenie Română",
            "Transcriirea unui certificat de naștere românesc / certificat de căsătorie",
            "Aplicarea mențiunii de încetare a căsătoriei sau de deces în România.",
            "Rectificarea actelor de stare civilă românești",
            "Reîntregirea familieii",
            "Înregistrarea căsătorii în străinătate pentru cetățenii moldoveni",
            "Înregistrarea căsătorii în străinătate pentru cetățenii români",
            "Echivalarea diplomei",
          ]
        },
        {
          title: "Permis de ședere",
          identifier: "permsed",
          subservices: [
            "Obținerea Permisului de ședere Ro",
            "Prelungirea Permisului de ședere Ro",
          ]
        },
        {
          title: "Permis de muncă",
          identifier: "permmun",
          subservices: [
          ]
        },
        {
          title: "Permis de Conducere",
          identifier: "permcon",
          subservices: [
            "Schimbul Permisului de Conducere Ro",
            "Prelungirea validității Permisului de Conducere Ro",
            "Restabilirea Permisului de Conducere Ro",
          ]
        },
        {
          title: "Obținerea alte acte/ certificate Ro",
          identifier: "obtact",
          subservices: [
            "Certificat de cazier judiciar",
          ]
        },
        {
          title: "Alte Servicii",
          identifier: "other",
          subservices: [
            "Apostilare Documente",
            "Traducere Documente",
            "Transport",
          ]
        },
      ]
    }),
    methods: {
      closeMenu() {
        this.services = false
        this.drawer = false
      },
      closeServices() {
        this.services = false
      },
      openServices() {
        this.services = true
      },
      closeSubservices() {
        this.subservices = false
      },
      openSubservices(id) {
        const arr = this.servicesItems.find(x => x.identifier === id);
        this.subserviceIdentifier = arr.subservices;
        this.subservices = true
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