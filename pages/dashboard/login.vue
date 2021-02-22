<template>
  <v-sheet class="auth">
    <div class="v-sheet auth__inner">
      <div class="v-card pa-4" light>
        <v-row class="d-flex auth__header justify-space-around">
          <div class="col-12">
            <h5 class="text-center">Sign in with</h5>
          </div>
          <div class="col-auto">
            <v-btn small color="primary">
              <v-icon>mdi-google</v-icon>
              Google
            </v-btn>
          </div>
          <div class="col-auto">
            <v-btn small color="primary">
              <v-icon>mdi-facebook</v-icon>
              Facebook
            </v-btn>
          </div>
        </v-row>
        <v-divider class="ma-4"></v-divider>
        <v-form class="row">
          <div class="col-12">
            <h5 class="text-center">Or sign in with credentials</h5>
          </div>
          <div class="col-12">
            <v-text-field
              label="Email"
              type="email"
            ></v-text-field>
          </div>
          <div class="col-12">
            <v-text-field
              label="Password"
              type="password"
            ></v-text-field>
          </div>
          <div class="col-12">
            <v-checkbox
              v-model="checkbox"
              label="Remember Me"
            ></v-checkbox>
          </div>
          <div class="col-12">
            <v-btn color="secondary" class="d-block">
              sign in
            </v-btn>
          </div>
        </v-form>
      </div>
      <v-sheet class="auth__other">
        <a href="#">Forgot Password?</a>
        <a href="#">Create new account</a>
      </v-sheet>
    </div>
  </v-sheet>
</template>

<script>
  

  export default {
    layout: "auth",
    name: "login",
    components: {
    },
    data() {
      return {
      };
    },
  };
</script>

<style lang="scss" scoped>
  .display-1 {
    color: $custom_blue !important;
    font-weight: 700 !important;   
  }
  .auth {
    height: 100vh;
    width: 100vw;
    background-color: #1a202c;
    background-image: url(https://demos.creative-tim.com/vue-notus/img/register_bg_2.2fee0b50.png);
    background-size: 100%;

    &__inner {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
      flex-direction: column;
    }

    &__header {
      justify-content: space-around;
      margin-bottom: 20px;
    }

    &__other {
      display: flex;
      justify-content: space-between;
      color: #ffff;
      background-color: transparent;
      margin-top: 10px;

      a {
        color: #ffff;
        font-size: 16px;
        text-decoration: none;
      }
    }

    form {
      margin-top: 20px;
      
    }

    .d-block {
      display: block !important;
      width: 100%;
      margin-bottom: 10px;
    }

    .v-card {
      background-color: #ffff;
      border-radius: 3px;
      padding: 15px;
      width: 100%;

      h5 {
        text-align: center;
      }
    }
  }

  @media (min-width: 430px) {
    .auth {
      &__inner {
        padding: 0 15px;
      }
      &__other {
        width: 400px;
      }
      .v-card {
        width: 400px;
        padding: 30px;
      }
    }
  }
</style>
