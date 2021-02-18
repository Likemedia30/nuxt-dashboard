<template>
  <v-sheet class="about-content">
    <v-card
        class="banner"
        dark
      >
        <v-img rounded src="https://demos.creative-tim.com/vue-argon-dashboard/img/theme/profile-cover.jpg" height="100%" ></v-img>
        <div class="banner__content">
          <v-card-title>
            Hello Jessica
          </v-card-title>
          <v-card-text>
            This is your profile page. You can see the progress you've made with your work
          </v-card-text>
          <v-btn href="#formInfo" small color="secondary" class="p-4">
            Edit
          </v-btn>
        </div>
    </v-card>
    <v-container grid-list-xl fluid class="grid-desk">
      <div class="v-sheet avatar-relative">
        <v-card class="avatar-image pb-5 mb-8">
        <v-img  src="https://demos.creative-tim.com/vue-argon-dashboard/img/theme/team-4-800x800.jpg">
        </v-img>
        <div class="edit">
              <v-btn color="primary" fab>
                <v-icon>mdi-pencil</v-icon>
              </v-btn>
        </div>
        <v-card-actions class="d-flex justify-center vbuttons">
          <v-switch :label="s1 ? 'Online': 'Offline'" v-model="s1"></v-switch>
        </v-card-actions>
        <v-card-actions>
              <v-row class="justify-space-around">
                <v-col class="col-auto">
                  <v-btn color="primary">View Manager's Page</v-btn>
                </v-col>
              </v-row>
        </v-card-actions>
        <v-card-text>
              <v-row class="justify-space-around">
                <v-col class="col">
                  <div class="heading text-center">
                    22
                  </div>
                  <div class="description text-center">
                    Calls
                  </div>
                </v-col>
                <v-col class="col">
                  <div class="heading text-center">
                    79
                  </div>
                  <div class="description text-center">
                    Messages
                  </div>
                </v-col>
                <div class="col">
                  <div class="heading text-center">
                    10
                  </div>
                  <div class="description text-center">
                    Assigned Clients
                  </div>
                </div>
              </v-row>
              <div class="row justify-center infoCust">
                <div class="col-auto">
                  <div class="heading text-center">Jessica Partin, 27</div>
                  <!-- <div class="description text-center">
                    Rol: Manager
                  </div> -->
                </div>
              </div>
              <div class="row justify-center infoCust">
                <div class="col-auto">
                  <div class="heading text-center">Creative Manager</div>
                </div>
              </div>
        </v-card-text>
      </v-card>
      </div>
      <v-card class="profile-edit">
        <v-card-header id="formInfo">
          <v-card-title  class="d-flex justify-space-between elevation-1">
            <h4>My account</h4>
            <v-btn color="primary">
              Save All
            </v-btn>
          </v-card-title>
          <v-card-title class="pb-0 mt-3">
            <h5 class="mb-0">User Info</h5>
          </v-card-title>
        </v-card-header>
        <v-card-text class="pt-0">
          <v-form class="row">
            <div class="col-md-6 col-12">
              <v-text-field
                label="Name / Prenume"
                required
              ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
                label="Email"
                required
              ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
                label="Telefon"
                required
              ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-dialog
              ref="menu"
              v-model="modal"
              :close-on-content-click="false"
              :return-value.sync="date"
              transition="scale-transition"
              offset-y
              min-width="auto"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-text-field
                  v-model="date"
                  label="Picker in menu"
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
                  @click="mdal = false"
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
            </v-dialog>
            </div>
            <div class="col-12">
              <v-btn color="secondary" class="mt-5">
              Save Info
            </v-btn>
            </div>
          </v-form>
          
        </v-card-text>
        <v-divider class="my-4"></v-divider>
        <v-card-title class="">
          <h5 class="mb-0">Account Password</h5>
        </v-card-title>
        <v-card-text>
          <v-form class="row">
            <div class="col-md-6 col-12">
              <v-text-field
              label="Password"
              type="password"
              disabled
            ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
              label="Repeat Password"
              type="password"
              required
            ></v-text-field>
            </div>
            <div class="col-12">
              <v-btn color="secondary" class="mt-4">
              Save Password
            </v-btn>
            </div>
          </v-form>
        </v-card-text>
        <v-divider class="my-4"></v-divider>
        <v-card-title class="">
          <h5 class="mb-0">Social Contacts</h5>
        </v-card-title>
        <v-card-text>
          <div class="row">
            <div class="col-auto" v-for="item in social" :key="item">
              <v-tooltip bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-icon large v-bind="attrs" v-on="on" color="info">
                  mdi-{{item}}
                </v-icon>
              </template>
              <span>{{item}}</span>
            </v-tooltip>
            </div>
            <div class="col-12">
              <v-btn color="primary" dark >
                Other
              <v-icon>mdi-plus</v-icon>
              </v-btn>
            </div>
            <div class="col-12">
              <v-select
                :items="social"
                label="Preferred communication channel "
              ></v-select>
            </div>
            <div class="col-12">
              <v-btn color="secondary" class="mt-4">
                Save Social Info
              </v-btn>
            </div>
          </div>
        </v-card-text>
        <v-divider class="my-4"></v-divider>
        <v-card-title class="">
          <h5 class="mb-0">Contact Information</h5>
        </v-card-title>
        <v-card-text>
          <v-form class="row">
            <div class="col-md-6 col-12">
              <v-text-field
              label="Address"
              required
            ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
              label="City"
              required
            ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
              label="Country"
              required
            ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
              label="Postal Code"
              required
            ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-textarea
              solo
              name="input-7-4"
              label="About Client"
              class="mt-3"
            ></v-textarea>
            </div>
            <div class="col-12">
              <v-btn color="secondary" class="mt-4">
              Save Contact Info
            </v-btn>
            </div>
          </v-form>
        </v-card-text>
        <v-divider class="my-4"></v-divider>
        <v-card-title class="">
          <h5 class="mb-0">Client's work information</h5>
        </v-card-title>
        <v-card-text>
          <v-form class="row">
            <div class="col-md-6 col-12">
              <v-text-field
                label="Company"
                required
              >
              </v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-text-field
                label="Positions"
                required
              ></v-text-field>
            </div>
            <div class="col-md-6 col-12">
              <v-select
                :items="roles"
                label="Roles"
              ></v-select>
            </div>
            <div class="col-md-6 col-12">
              <v-select
                :items="langs"
                label="Language"
              ></v-select>
            </div>
            <div class="col-12">
              <v-btn color="secondary" class="mt-4">
                Save Work Info
              </v-btn>
            </div>
          </v-form>
          
        </v-card-text>
        <v-divider class="my-4"></v-divider>
        <v-card-title class="d-flex justify-center">
          <v-btn color="primary" large class="mt-3 mb-3">
            Save All
          </v-btn>
        </v-card-title>
      </v-card>
    </v-container>
  </v-sheet>
</template>

<script>
  import NameCard from '@/components/widgets/card/NameCard';
  import ProfileCard from '@/components/widgets/card/ProfileCard';
  import MessageList from '@/components/widgets/list/MessageList';
  import NotificationList from '@/components/widgets/list/NotificationList';
  import {Items as Users} from '@/api/user';
  import VWidget from '@/components/VWidget';

  export default {
    layout: "dashboard",
    name: "client-one",
    components: {
      NameCard,
      ProfileCard,
      MessageList,
      NotificationList,
      VWidget
    },
    data() {
      return {
        date: null,
        menuDate: false,
        modal: false,
        s1: false,
        langs: [
          "RO",
          "RU",
          "EN"
        ],
        roles: [
          "Client",
          "Manager",
          "PM"
        ],
        social: [
          "facebook-messenger",
          "instagram", 
          "whatsapp",
          "telegram",
          "facebook"
        ]
        
      };
    },
    mounted() {
      this.arrayEvents = [...Array(6)].map(() => {
        const day = Math.floor(Math.random() * 30);
        const d = new Date();
        d.setDate(day);
        return d.toISOString().substr(0, 10);
      });
    },
    computed: {
      posts() {
        return getPost();
      }
    },
    methods: {
      functionEvents(date) {
        const [, , day] = date.split('-');
        return parseInt(day, 10) % 3 === 0;
      },
      handleClick: (e) => {
        console.log(e);
      }
    }
  };
</script>

<style lang="scss" scoped>
  .display-1 {
    color: $custom_blue !important;
    font-weight: 700 !important;   
  }

  .about-content {
    p {
      color: $custom_red !important
    }

    .banner {
      height: 70vh;
      position: relative;
      

      &__content {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 3;
        display: flex;
        justify-content: flex-start;
        flex-direction: column;
        padding: 0 30px;
        padding-top: 50px;
      }

      .v-card__title {
        text-align: left;
      }

      .v-card__text {
        text-align: left !important;
      }

      .v-btn {
        margin-left: 16px;
        max-width: 150px;
      }

      .v-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
        position: absolute;
        z-index: 1;
        top: 0;
        left: 0;
      }

      &:after {
        content: "";
        position: absolute;
        left: 0;
        right: 0;
        width: 100%;
        height: 100%;
        background-color: rgba($color: $custom_blue, $alpha: 0.7);
        z-index: 2;
      }
    }

    .avatar-relative {
      position: relative;
      top: -80px;
      z-index: 4;
      max-width: 400px;
      min-width: 350px;
      margin-left: auto;
      margin-right: auto;
    } 
  }
  .avatar-image {
    padding-top: 80px;

    .heading {
      font-size: 25px;
      color: $custom_blue;
      font-weight: bold;
    }

    .description button {
      text-decoration: underline;
    }

    .infoCust {
      .description {
        margin-top: 10px;
      }
      button {
        font-weight: normal;
        color: inherit;
      }
    }
  }

  .avatar-image .v-image {
    position: absolute;
    width: 160px;
    height: 160px;
    top: -79px;
    left: calc(50% - 80px);
    border-radius: 50% !important;
  }
  .avatar-image .edit {
    position: absolute;
    top: 30px;
    left: 200px
  }

  @media (min-width: 991px) {
    .grid-desk {
      display: flex;
    }
    .profile-edit {
      order: 1;
      margin-right: 20px;
      position: relative;
      top: -80px;
      z-index: 2;
      
    }
    .avatar-relative {
      order: 2;
    }
  }
</style>
