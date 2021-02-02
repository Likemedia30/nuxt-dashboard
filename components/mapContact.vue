<template>
  <section class="map-contact">
    <div class="container">
      <div class="row">
        <div class="col-lg-5 col-md-6 col-12">
          <v-card class="hours-plan">
            <h5>Working Hours</h5>
            <p>Check out Montan Dentist’s Office hours to plan your visit.</p>
            <ul>
              <li><span>Monday</span><span>8AM-9PM</span></li>
              <li><span>Tuesday</span><span>8AM-9PM</span></li>
              <li><span>Wednesday</span><span>9AM-6:30PM</span></li>
              <li><span>Thursday</span><span>8AM-9PM</span></li>
              <li><span>Friday</span><span>8AM-9PM</span></li>
              <li><span>Saturday-Sunday</span><span>Closed</span></li>
            </ul>
            <h5>Need Flexible Time?</h5>
            <v-dialog
              v-model="dialog"
              max-width="600px"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  color="secondary"
                  dark
                  v-bind="attrs"
                  v-on="on"
                >
                  <v-icon left>mdi-book-open</v-icon>
                  Programează-te
                </v-btn>
              </template>
              <v-card>
                <v-card-title>
                  <span class="headline">Programează-te</span>
                </v-card-title>
                <v-card-text>
                  <v-container>
                    <v-row>
                      <v-col
                        cols="12"
                        sm="12"
                        md="12"
                      >
                        <v-text-field
                          label="Nume*"
                          required
                          hint="Introduceți numele"
                        ></v-text-field>
                      </v-col>
                      <v-col
                        cols="12"
                        sm="12"
                        md="12"
                      >
                        <v-text-field
                          label="Email*"
                          required
                          hint="Introduceți email"
                        ></v-text-field>
                      </v-col>
                      <v-col
                        cols="12"
                        sm="12"
                        md="12"
                      >
                        <v-text-field
                          label="Numărul de telefon*"
                          required
                          hint="Introduceți un număr de telefon valid"
                        ></v-text-field>
                      </v-col>
                    </v-row>
                  </v-container>
                  <small>*indicates required field</small>
                </v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    color="primary"
                    text
                    @click="dialog = false"
                  >
                    Close
                  </v-btn>
                  <v-btn
                    color="primary"
                    text
                    @click="dialog = false"
                  >
                    Send
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </v-card>
        </div>
      </div>
    </div>
    <div class="mapouter">
      <div class="gmap_canvas">
        <iframe
          id="gmap_canvas"
          src="https://maps.google.com/maps?q=bucuresti&t=&z=13&ie=UTF8&iwloc=&output=embed"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
        ></iframe>
        <a href="https://www.embedgooglemap.net"></a>
      </div>
      <style>
        .mapouter {
          text-align: right;
          height: 100%;
          width: 100%;
        }
        .gmap_canvas {
          overflow: hidden;
          background: none !important;
          height: 100%;
          width: 100%;
        }
      </style>
    </div>
  </section>
</template>
<script>
export default {
  name: "MapContact",
  data: () => (
    {
      dialog: false
    }
  )
}
</script>

<style lang="scss">
  .map-contact {
    padding: 0;
    position: relative;
    z-index: 1;

    .col-12 {
      padding: 0;
    }

    .hours-plan {
      background: $custom_blue;
      padding: 80px 15px;
      position: relative;
      z-index: 2;

      img {
        margin-bottom: 30px;
      }

      h5 {
        font-size: 20px;
        color: $custom_yellow;
        line-height: 1.1;
        margin-bottom: 20px;
      }

      li,
      p {
        font-size: 16px;
        color: #ffff;
        line-height: 1.1;
      }

      p {
        margin-bottom: 10px;
      }

      li {
        display: flex;
        justify-content: space-between;
        padding: 10px 0;
        border-bottom: 1px solid rgba($color: rgb(133, 133, 133), $alpha: 0.85);

        span:last-child {
          color: rgba($color:  rgb(193, 193, 193), $alpha: 0.85);
        }
      }

      ul {
        margin-bottom: 40px;
        padding-left: 0;
      }

      .button {
        span {
          color: #fff;
        }

        #arrow {
          fill: #fff;
        }
      }
    }

    .mapouter {
      top: 0;
      right: 0;
      width: 100vw;
      height: 100%;
      min-height: 500px;
      z-index: 1;
      filter: grayscale(100%);
    }

    iframe {
      width: 100%;
      height: 100%;
      min-height: 500px;
    }
  }

  @media (min-width: 991px) {
      .map-contact {
        padding: 80px 0;

        .hours-plan {
          padding: 40px;
        }
        .mapouter {
          position: absolute;
          width: 100vw;
          height: 70vh;
        }
      }
  }
</style>