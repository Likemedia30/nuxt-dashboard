<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <v-stepper v-model="e1" class="calendar">
          <v-stepper-header>
            <v-stepper-step
              :complete="e1 > 1"
              step="1"
            >
              Choose Date
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step
              :complete="e1 > 2"
              step="2"
            >
              Confirm Meeting
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step step="3">
              Terms and Conditions
            </v-stepper-step>
          </v-stepper-header>

          <v-stepper-items>
            <v-stepper-content step="1">
              <v-sheet
                class="mb-12"
              >
                <div class="row justify-space-around">
                  <div class="col-12">
                    <div class="title text-center font-weight-bold">
                      Meeting with Maximilian Aue
                    </div>
                  </div>
                  <div class="col-lg-auto col-12">
                    <v-date-picker
                      v-model="picker"
                      color="primary lighten-1"
                    ></v-date-picker>
                  </div>
                  <div class="col-lg-auto col-12">
                    <div class="title">
                      Alege Durata
                    </div>
                    <v-radio-group
                      v-model="ex8"
                      row
                    >
                      <v-radio
                        label="5 min"
                        color="primary"
                        value="5"
                      ></v-radio>
                      <v-radio
                        label="15 min"
                        color="primary"
                        value="15"
                      ></v-radio>
                      <v-radio
                        label="30 min"
                        color="primary"
                        value="30"
                      ></v-radio>
                    </v-radio-group>
                    <div class="title mb-4">
                      Alege ora pentru consultatie
                    </div>
                    <v-select
                      :items="items"
                      label="Fusul orar"
                      outlined
                      append-outer-icon="mdi-earth"
                    ></v-select>
                    <v-select
                      v-model="e2"
                      :items="hours"
                      append-outer-icon="mdi-archive-clock"
                      menu-props="auto"
                      hide-details
                      label="8:00"
                      single-line
                      outlined
                    ></v-select>
                  </div>
                </div>
              </v-sheet>

              <v-btn
                color="primary"
                @click="e1 = 2"
              >
                Continue
              </v-btn>

              <v-btn text>
                Cancel
              </v-btn>
            </v-stepper-content>

            <v-stepper-content step="2">
              <v-card
                class="mb-12 py-8"
              >
                <v-sheet>
                  <div class="row justify-center">
                    <div class="col-lg-4 col-md-6 col-12">
                      <div class="title font-weight-bold text-center">
                        Friday, January 15, 2021 1:15 PM
                      </div>
                      <v-form v-model="valid">
                        <v-text-field
                          label="First name"
                          required
                        ></v-text-field>
                        <v-text-field
                          label="Last name"
                          required
                        ></v-text-field>
                        <v-text-field
                          label="Email"
                          required
                        ></v-text-field>
                      </v-form>
                    </div>
                  </div>
                </v-sheet>
              </v-card>

              <v-btn
                color="primary"
                @click="e1 = 3"
              >
                Continue
              </v-btn>

              <v-btn text>
                Cancel
              </v-btn>
            </v-stepper-content>

            <v-stepper-content step="3">
              <v-card
                class="mb-12 py-8"

              >
              
                <div class="row justify-center">
                  <div class="col-md-6">
                    <div class="title font-weight-bold text-center mb-4">
                      Terms And Conditions
                    </div>
                    <p>
                      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nesciunt, odio culpa non alias laudantium officiis?
                    </p>
                    <v-checkbox
                      label="I agree to receive other communications from Tienda"
                      color="primary"
                      value="false"
                      hide-details
                      class="mb-3"
                    ></v-checkbox>
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Qui eum reprehenderit inventore nostrum nihil beatae iure voluptates eligendi, nulla pariatur.
                  </div>
                </div>
              </v-card>

              <v-btn
                color="primary"
                @click="e1 = 1"
              >
                Continue
              </v-btn>

              <v-btn text>
                Cancel
              </v-btn>
            </v-stepper-content>
          </v-stepper-items>
        </v-stepper>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        e1: 1,
        picker: new Date().toISOString().substr(0, 10),
        picker2: new Date().toISOString().substr(0, 10),
        ex8: "5",
        items: [
          "UTC +02:00 Eastern European Time",
          "UTC +02:00 Eastern European Time",
          "UTC +02:00 Eastern European Time",
          "UTC +02:00 Eastern European Time",
          "UTC +02:00 Eastern European Time",
          "UTC +02:00 Eastern European Time",
        ],
        hours: [
          "8:00",
          "8:30",
          "9:00",
          "9:40",
          "10:00",
          "10:30",
          "11:00",
          "11:30",
          "12:00",
          "12:30",
        ]
      }
    },
  }
</script>

<style scoped>
  .calendar {
    padding-top: 56px;
  }

  @media (min-width: 991px) {
    .calendar {
      padding-top: 150px;
    }
  }
</style>