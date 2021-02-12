<template>
  <div class="row cabinet-content">
    <div class="col-lg-10 col-md-12 col-12 display-1 text-center">
      Datele personale
    </div>
    <div class="col-lg-10 col-md-12 col-12">
      <v-form
        ref="form"
        class="row"
        lazy-validation
      >
        <div class="col-md-6">
          <v-text-field
          label="Nume"
          required
        ></v-text-field>
        </div>

        <div class="col-md-6">
          <v-text-field
          label="Prenume"
          required
        ></v-text-field>
        </div>
        <div class="col-6">
          <label>
            Gen
          </label>
          <v-radio-group v-model="radioGroup" class="d-flex">
            <v-radio
              label="Masculin"
            ></v-radio>
            <v-radio
              label="Femenin"
            ></v-radio>
          </v-radio-group>
        </div>

        <div class="col-6">
          <label>Data Nasterii</label>
          <v-menu
            ref="menu"
            v-model="dateMenu"
            :close-on-content-click="false"
            :return-value.sync="date"
            transition="scale-transition"
            offset-y
            min-width="auto"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                v-model="date"
                prepend-icon="mdi-calendar"
                readonly
                v-bind="attrs"
                v-on="on"
              ></v-text-field>
            </template>
            <v-date-picker
              v-model="date"
              no-title
              scrollable
            >
              <v-spacer></v-spacer>
              <v-btn
                text
                color="primary"
                @click="menu = false"
              >
                Cancel
              </v-btn>
              <v-btn
                text
                color="primary"
                @click="$refs.menu.save(date)"
              >
                OK
              </v-btn>
            </v-date-picker>
          </v-menu>
        </div>

        <div class="col-md-6">
          <v-text-field
          label="Telefon"
          required
        ></v-text-field>
        </div>
        <div class="col-md-6">
          <v-text-field
          label="E-mail"
          required
        ></v-text-field>
        </div>
        <div class="col-md-6">
          <v-text-field
          label="Resetați parola"
          type="password"
          required
        ></v-text-field>
        </div>

        <div class="col-md-6">
          <v-text-field
          label="Repetați parola"
          type="password"
          required
        ></v-text-field>
        </div>
        <div class="col-12">
          <v-btn
          color="secondary"
          >
            Save
          </v-btn>
        </div>
      </v-form>
    </div>
  </div>
</template>

<script>
export default {
  layout: "cabinet",
  components: {

  },
  data: () => ({
    date: new Date().toISOString().substr(0, 10),
    dateMenu: false,
    radioGroup: 1
  }),
}
</script>

<style lang="scss">
  .cabinet-content {
    .radiogroup {
      flex-direction: row;
    }

    
  }

</style>
