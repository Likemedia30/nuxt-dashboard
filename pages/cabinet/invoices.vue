<template>
  <div class="row cabinet-content">
    <div class="col-lg-10 col-md-12 col-12 display-1 text-center my-5">
      Comanda Nr 3
    </div>
    <div class="col-12">
      <v-expansion-panels accordion>
        <v-expansion-panel v-for="(item, i) in 3" :key="i" class="mb-6">
          <v-expansion-panel-header >
            <v-subtitle class="font-weight-bold">
              2 feb 2021
            </v-subtitle>
            <v-subtitle>Ending balance: $30</v-subtitle>
          </v-expansion-panel-header>
          
          <v-expansion-panel-content>
            <v-subtitle>Documents (2)</v-subtitle>
            <v-sheet class="mb-3 mt-3">
              <div class="caption">
                <span class="d-block">
                  CSV Invoice (1)
                </span>
                <span class="d-block">
                  <a download="">120321903 (created: 12/03/2020)</a>
                </span>
              </div>
            </v-sheet>
            <v-sheet>
              <div class="caption">
                <span class="d-block">
                  PDF Invoice (1)
                </span>
                <span class="d-block">
                  <a download="">120321903 (created: 12/03/2020)</a>
                </span>
              </div>
            </v-sheet>
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
