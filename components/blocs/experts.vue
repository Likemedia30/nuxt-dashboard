<template>
      <section class="experts">
        <v-container>
          <v-row>
            <v-col cols="12">
              <div class="display-1 text-center c-title">
                Discută live cu experții noștri
              </div>
              <p class="text-center text">
                Suntem mândri că am reușit să formăm o echipă de frunte printre prestatorii de top ai serviciilor juridice. O echipă cu care putem mereu onora misiunea pe care ne-am asumat-o.
              </p>
            </v-col>
            <v-col 
              v-for="(item, i) in experts"
              :key="i"
              class="col-lg-4 col-md-6 col-12 d-flex child-flex"
              
              >
              <v-card>
                <v-img
                  :src="item.src"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                </v-img>
                <v-card-title class="title justify-center">
                  {{item.name}}
                </v-card-title>
                <v-card-subtitle class="text-center">
                  {{item.role}}
                </v-card-subtitle>
                <v-card-actions
                  class="pb-5 justify-center"
                >
                  <v-btn
                    color="secondary"
                  >
                    <v-icon left>mdi-phone</v-icon>
                    Sună
                  </v-btn>

                  <v-btn
                    color="info"
                  >
                    <v-icon left>mdi-chat</v-icon>
                    Chat
                  </v-btn>
                  
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>
</template>

<script>
export default {
  data: () => ({
    experts: [
      {
        name: "Lilia Balan",
        role: "Jurist",
        src: "https://image.tmdb.org/t/p/original/hs2xlX7jAgY0dib1RPmjMjqVLMC.jpg"
      },
      {
        name: "Ion Neaga",
        role: "Jurist",
        src: "https://images.pexels.com/photos/220453/pexels-photo-220453.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500"
      },
      {
        name: "Andrei Mancu",
        role: "Jurist",
        src: "https://monkey47.com/thumbs/species-rara/mark-braun/mark-braun-500x750-q75.jpg"
      },
    ],
  })
}
</script>

<style lang="scss">
</style>
