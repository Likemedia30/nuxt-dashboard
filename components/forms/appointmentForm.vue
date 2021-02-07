<template>
  <v-dialog max-width="500" v-model="dialog">
    <v-card>
      <v-card-title>
        <span class="headline">Programează-te</span>
      </v-card-title>
      <validation-observer>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                sm="12"
                md="12"
              >
                <validation-provider v-slot="{ errors }"
                    name="Name"
                    rules="required|max:10">
                  <v-text-field
                    v-model="name"
                    :counter="10"
                    :error-messages="errors"
                    label="Nume*"
                    required
                    hint="Introduceți numele"
                  ></v-text-field>
                </validation-provider>
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
            @click.native="dialog = false"
          >
            Close
          </v-btn>
          <v-btn
            color="primary"
            text
            @click.native="dialog = false"
          >
            Send
          </v-btn>
        </v-card-actions>
      </validation-observer>
    </v-card>
  </v-dialog>
</template>

<script>
  import { required, digits, email, max, regex } from 'vee-validate/dist/rules'
  import { extend, ValidationObserver, ValidationProvider, setInteractionMode } from 'vee-validate';

    setInteractionMode('eager')

  extend('digits', {
    ...digits,
    message: '{_field_} needs to be {length} digits. ({_value_})',
  })

  extend('required', {
    ...required,
    message: '{_field_} can not be empty',
  })

  extend('max', {
    ...max,
    message: '{_field_} may not be greater than {length} characters',
  })

  extend('regex', {
    ...regex,
    message: '{_field_} {_value_} does not match {regex}',
  })

  extend('email', {
    ...email,
    message: 'Email must be valid',
  })

  export default {
    name: "AppointmentForm",
    components: {
      ValidationProvider,
      ValidationObserver,
    },
    data: () => (
      {
        dialog: false,
        name: ''
      }
    ),
    methods: {
      submit () {
        this.$refs.observer.validate()
      },
      clear () {
        this.name = ''
        this.phoneNumber = ''
        this.email = ''
        this.select = null
        this.checkbox = null
        this.$refs.observer.reset()
      },
    },
    created() {
      this.$nuxt.$on('open-appointment-form', () => {
        this.dialog = true
      })
    },
    beforeDestroy(){
      this.$nuxt.$off('open-appointment-form')
    }
  }
</script>