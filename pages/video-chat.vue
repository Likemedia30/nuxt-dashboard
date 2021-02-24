<template>
  <div class="d-flex">
    <div class="video">
      <div  class="video__top d-flex justify-space-between">
        <v-sheet dark>
          <v-btn small dark>
            <v-icon>
              mdi-information
            </v-icon>
          </v-btn>
          <v-btn dark small class="ml-3">
            <v-icon>
              mdi-cog
            </v-icon>
          </v-btn>
        </v-sheet>
        <v-btn dark small @click="handleFullScreen()">
          <v-icon>
            mdi-fullscreen
          </v-icon>
        </v-btn>
      </div>
      <div class="video-container">

      </div>
      <video-bottom></video-bottom>
    </div>
    <chat v-show="chatDrawer" />
  </div>
</template>

<script>
import VideoBottom from '@/components/video/video-bottom';
import chat from '@/components/video/chat';
import Util from '@/util';

export default {
  layout: "video",
  components: {
    VideoBottom,
    chat
  },
  data: () => ({
    chatDrawer: false,
    
  }),
  methods: {
    handleFullScreen() {
        Util.toggleFullScreen();
      },
  },
  created() {
    this.$nuxt.$on('openChat', () => {
      this.chatDrawer = !this.chatDrawer
    })
  },
  beforeDestroy(){
    this.$nuxt.$off('openChat')
  }
}
</script>

<style lang="scss">
  .video {
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

      .v-sheet {
        background: rgb(34, 34, 34);
      }
    }

    .video-container {
      height: 100%;
    }
  }
</style>

