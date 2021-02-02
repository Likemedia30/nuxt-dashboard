<template>
  <main>
      <div class="banner">
        <v-carousel :show-arrows="false" cycle>
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
          >
            <v-container class="fill-height">
              <v-row
                class="fill-height"
                align="center"
                justify="center"
              >
                <v-col md12 class="text-center">
                  <div class="display-1 text-center c-title">
                    {{ item.text }}
                  </div>
                  <v-sheet
                    class="c-sheet"
                    elevation="1"
                    height="auto"
                    width="auto"
                    
                  >
                    Consultație gratuită
                  </v-sheet>
                </v-col>
              </v-row>
            </v-container>
          </v-carousel-item>
        </v-carousel>
      </div>
      <div class="callNow">
        <v-parallax height="200" src="call-now-bg.png">
          <v-container>
            <v-row>
              <v-col>
                <v-sheet
                  class="c-sheet text-center"
                  elevation="0"
                  height="auto"
                  width="auto"
                  >
                  
                  <v-btn
                    class="ma-2 btn-yell"
                    x-large
                    color="secondary"
                  > 
                    <v-icon left>mdi-comment-bookmark</v-icon>
                    Consultație gratuită
                  </v-btn>
                </v-sheet>
                
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>

      </div>
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
              <v-card>
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
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <div class="callNow">
        <v-parallax height="200" src="call-now-bg.png">
          <v-container>
            <v-row>
              <v-col>
                <v-sheet
                  class="c-sheet text-center"
                  elevation="0"
                  height="auto"
                  width="auto"
                  >
                  
                  <v-btn
                    class="ma-2 btn-yell"
                    x-large
                    color="secondary"
                  > 
                    <v-icon left>mdi-comment-bookmark</v-icon>
                    Consultație gratuită
                  </v-btn>
                </v-sheet>
                
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>

      </div>
      <section class="testimonials">
        <v-container>
          <v-row>
            <v-col cols="12">
              <div class="display-1 text-center">
                Clienții Noștri
              </div>
            </v-col>
            <v-col cols="12">
              <testimonial></testimonial>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <map-contact></map-contact>
  </main>
</template>

<script>
import Testimonial from "@/components/sliders/testimonial"
import MapContact from "@/components/mapContact.vue"
export default {
  layout: "default",
  components: {
    Testimonial,
    MapContact
  },
  data: () => ({
    items: [
      {
        src: 'banner.jpg',
        text: 'Cetățenie Română'
      },
      {
        src: 'banner.jpg',
        text: 'Programări online'
      },
      {
        src: 'banner.jpg',
        text: 'Obținerea pașaportului românesc'
      },
      {
        src: 'banner.jpg',
        text: 'Programări online'
      },
    ],
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
    
  }),
}
</script>

<style lang="scss">

  .display-1 {
    color: $custom_blue !important;
    font-weight: 700 !important;   
  }
  
  .banner {

    .c-title {
      color: $custom_blue;
      font-weight: 900 !important;
      margin-bottom: 5rem;
    }

    .c-sheet {
      padding: 20px;
      text-align: center;
      display: inline;
      background: rgba($color: $custom_red, $alpha: 1);
    }

    .v-responsive__content {
      background-color: rgba($color: #ffff, $alpha: 0.8);
    }
  }
  .callNow {
    .c-sheet {
      background: transparent;
    }

    .btn-yell {
      background: $custom_yellow !important;
      color: #000000 !important;
    }
  }

  .experts {
    background-color: $custom_blue;
    .display-1 {
      color: #ffff !important;
    }

    .text {
      color: #ffff;
      max-width: 500px;
      margin: 20px auto;
    }
  }

  section {
    padding: 50px 0;
  }
  @media (min-width: 767px) {
    .banner {
      
      .v-window,
      .v-carousel__item {
        min-height: 80vh;
      }
    }
  }
</style>
