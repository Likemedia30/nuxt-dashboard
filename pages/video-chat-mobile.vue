<template>
  <div class="d-flex">
    <div class="video-mobile">
      <div  class="video-mobile__top d-flex justify-space-between">
        <v-sheet dark>
          <v-btn small dark>
            <v-icon>
              mdi-volume-high
            </v-icon>
          </v-btn>
          <v-btn dark small>
            <v-icon>
              mdi-camera-flip
            </v-icon>
          </v-btn>
        </v-sheet>
        <v-btn
          @click.stop="drawerInfo = !drawerInfo"
          small
          dark
        >
          VideoChat
          <v-icon>
            mdi-chevron-down
          </v-icon>
        </v-btn>
        <v-sheet dark class="but-end">
          <v-btn height="30" width="40" small dark  color="secondary">
            End
          </v-btn>
        </v-sheet>
      </div>
      <div class="video-mobile-container">

      </div>
      <video-bottom-mobile></video-bottom-mobile>
    </div>
    <v-navigation-drawer class="infoChat" v-model="drawerInfo"
      absolute
      bottom
      temporary
      dark
      >
      <v-card dark class="elevation-6">
        <v-card-title>
          Andrei Tintari's meeting
        </v-card-title>
        <v-card-text>
          <v-sheet>
            <div class="menuItem">
              <span>Meeting Id</span>
              <span>893 341 324 234</span>
            </div>
            <div class="menuItem">
              <span>Host</span>
              <span>Andrei Tintari</span>
            </div>
            <div class="menuItem">
              <span>Invite Link</span>
              <span>http://videochat/r/1232343221QW23</span>
            </div>
            <div class="menuItem">
              <span>Participant Id</span>
              <span>45671</span>
            </div>
            <div class="menuItem">
              <span>Encription</span>
              <span>Enabled</span>
            </div>
            <p>You are connected to videochat via data centers in the Romania </p>
          </v-sheet>
        </v-card-text>
      </v-card>
    </v-navigation-drawer>
    <v-navigation-drawer class="infoChat" v-model="drawerMenu"
      absolute
      bottom
      temporary
      light
      >
      <v-card light>
        <v-card-text>
          <v-list>
            <v-list-item  color="secondary">
              <v-list-item-title> 
                Disconnect Audio
              </v-list-item-title>
              
            </v-list-item>
            <v-list-item>
              <v-list-item-title color="secondary"> 
                Security
              </v-list-item-title>
              <v-icon>
                mdi-security
              </v-icon>
            </v-list-item>
            <v-list-item>
              <v-list-item-title color="secondary"> 
                Chat
              </v-list-item-title>
              <v-icon>
                mdi-chat
              </v-icon>
            </v-list-item>
            <v-list-item>
              <v-list-item-title color="secondary"> 
                Meeting Settings
              </v-list-item-title>
              <v-icon>
                mdi-cog
              </v-icon>
            </v-list-item>
          </v-list>
        </v-card-text>
        <v-card-text>
          <div class="emoticons">
            &#x1F354
          </div>
        </v-card-text>
      </v-card>
    </v-navigation-drawer>
    <chat v-show="chatDrawer" />
  </div>
</template>

<script>
import VideoBottomMobile from '@/components/video/video-bottom-mobile';
import chat from '@/components/video/chat';

export default {
  layout: "video",
  components: {
    VideoBottomMobile,
    chat
  },
  data: () => ({
    chatDrawer: false,
    drawerMenu: false,
    drawerInfo: false
  }),
  methods: {
    onClick () {
        // Perform an action
      }
  },
  created() {
    this.$nuxt.$on('openChat', () => {
      this.chatDrawer = !this.chatDrawer
    }),
    this.$nuxt.$on('openMenuMobile', () => {
      this.drawerMenu = !this.drawerMenu
    })
  },
  beforeDestroy(){
    this.$nuxt.$off('openChat')
  }
}
</script>

<style lang="scss">
  .video-mobile {
    width: 100%;
    height: 100vh;
    background: rgb(34, 34, 34);
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    &__menu-bottom {
      position: static;
    }

    &__top {
      padding: 15px;
      align-items: center;

      .v-sheet {
        background: none;
        
        padding: 0;
      }

      .v-btn {
        padding: 0 !important;
        box-shadow: none !important;
        background: transparent;
        min-width: 25px !important;
      }
    }

    .video-mobile-container {
      height: 100%;
    }

    .but-end {
      padding-left: 15px;

      .v-btn span {
        color: #ffff
      }
    }
  }
  .infoChat {
    max-height: 80% !important;

    .v-sheet {
      height: 100%;
    }
  }
  .infoChat .menuItem {
      display: flex;
      margin-bottom: 15px;

      span:first-child {
        width: 40%;
        opacity: 0.6;
      }
      span:last-child {
        width: 60%;
      }
    }
</style>

