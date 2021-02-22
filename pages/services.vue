<template>
 <main>
    <section class="services">
        <v-container>
          <v-row>
            <v-col cols="12">
              <div class="display-1 text-center c-title">
                Servicii
              </div>
            </v-col>
            <v-col 
              v-for="(item, i) in servicesSection"
              :key="i"
              class="col-lg-4 col-md-6 col-12 d-flex child-flex"
              
              >
              <v-card exact nuxt to="/expert-one">
                <v-img
                  :src="item.src"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                </v-img>
                <v-card-title class="title">
                  {{item.title}}
                </v-card-title>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>
 </main>
</template>

<script>
export default {
  data: () => ({
    
    servicesSection: [
      {
        title: "Cetațenia română",
        src: "cetro.png"
      },
      {
        title: "Permis de ședere",
        src: "permsed.png"
      },
      {
        title: "Permis de muncă",
        src: "work.png"
      },
      {
        title: "Permis de Conducere",
        src: "permcond.png"
      },
      {
        title: "Obținerea alte acte/ certificate Ro",
        src: "lavoro.png"
      },
      {
        title: "Alte Servicii",
        src: "other.png"
      },
    ],
  })
}
</script>

<style lang="scss">
</style>
