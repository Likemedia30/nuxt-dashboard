<template>
  <div class="row cabinet-content">
    <div class="col-lg-10 col-md-12 col-12 display-1 text-center my-5">
      Eu urmăresc
    </div>
    <div class="col-lg-10 col-12">
      <p class="text-center">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo quas dignissimos obcaecati incidunt laborum? Iste voluptatum praesentium doloribus corporis, cum, pariatur sint eius fugiat laborum et est quo quidem maiores.
      </p>

      <v-sheet class="mySubscribes">
        <div color="primary" class="cust-title my-6">
          Urmăriri
        </div>
        <v-sheet>
          <v-checkbox
            v-for="(item, i) in check"
            :key="i"
            :v-model="item.name"
            :label="item.label"
            color="primary"
            :value="item.label"
            hide-details
            class="mt-1"
          ></v-checkbox>
        </v-sheet>
      </v-sheet>
      <v-divider class="my-6"></v-divider>
      <v-btn color="secondary">
        Save
      </v-btn>
      <v-sheet>
        <label class="caption">
          În cazul în care nu salvați, schimbările vor fi anulate.
        </label>
      </v-sheet>
    </div>
  </div>
</template>

<script>
export default {
  layout: "cabinet",
  components: {

  },
  data: () => ({
    check: [
      {
        name: false,
        label: "Reduceri"
      },
      { 
        name: false,
        label: "Articole de la experți"
      },
      {
        name: false,
        label: "Exemplu 2"
      },
      {
        name: false,
        label: "Exemplu 4",
      },
      {
        name: false,
        label: "Exemplu 5"
      }
    ]
  }),
}
</script>

<style lang="scss">
  .cust-title {
    font-size: 25px;
    font-weight: 700;
  }
  .mySubscribes label {
    text-transform: uppercase;
  }

  p {
    font-size: 18px !important;
  }
</style>
