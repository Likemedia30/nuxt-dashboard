<template>
  <div class="row cabinet-content">
    <div class="col-lg-10 col-md-12 col-12 display-1 text-center my-5">
      Comanda Nr 3
    </div>
    <div class="col-12">
      <v-expansion-panels accordion>
        <v-expansion-panel class="mb-6">
          <v-expansion-panel-header class="font-weight-bold">Documente</v-expansion-panel-header>
          
          <v-expansion-panel-content>
            <v-subtitle class="mb-4 d-block">
              Incarcati actele solicitate mai jos
            </v-subtitle>
            <v-sheet v-for="(item, i) in 4"
                :key="i">
              <v-sheet class="py-0 d-flex justify-space-between align-center">
                <v-subtitle>Buletin de identitate</v-subtitle>
                <v-btn color="secondary" type="file">
                  <v-icon>mdi-plus</v-icon>
                  Add
                </v-btn>
              </v-sheet>
              <p class="caption pa-0">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste, tenetur!
              </p>
              <v-divider class="mb-4"></v-divider>
            </v-sheet>
            <p class="caption">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit.
            </p>
            <v-checkbox
            v-model="check1"
            value="check1"
            color="primary"
            label="I have read and accept the Merchant Account terms"
            hide-details
            class="mt-1"
          ></v-checkbox>
          <v-checkbox
            v-model="check2"
            value="check2"
            color="primary"
            label="I have read and accept the Merchant Account terms Lorem, ipsum dolor sit amet consectetur adipisicing elit. Aspernatur natus quidem illo est delectus pariatur itaque placeat atque ipsa id!"
            hide-details
            class="mt-1"
          ></v-checkbox>
          <v-checkbox
            v-model="check3"
            value="check3"
            color="primary"
            label="I have read and accept the Merchant Account terms Lorem ipsum dolor sit amet."
            hide-details
            class="mt-1"
          ></v-checkbox>
          </v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel >
          <v-expansion-panel-header class="font-weight-bold">
            Descrierea Serviciului
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            <p class="caption">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Id recusandae reiciendis at. Corrupti ratione quidem maxime ducimus tempora, mollitia delectus illo iure molestiae sequi, reiciendis provident id possimus numquam. Corrupti.
            </p>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </div>
  </div>
</template>

<script>
export default {
  layout: "cabinet",
  components: {
  },
  data: () => ({
    check1: false,
    check2: false,
    check3: false
  }),
}
</script>

<style lang="scss">

</style>
