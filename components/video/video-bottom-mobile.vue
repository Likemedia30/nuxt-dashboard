<template>
  <v-bottom-navigation
    class="video-mobile__menu-bottom"
    :value="value"
    color="accent"
    dark
  > 
      <v-btn small>
        <span>Mute</span>
        <v-icon>mdi-microphone</v-icon>
      </v-btn>
      <v-btn small>
        <span>Stop Video</span>
        <v-icon>mdi-film</v-icon>
      </v-btn>
      <v-btn small @click="$nuxt.$emit('openChat')">
        <span>Chat</span>
        <v-icon>mdi-chat</v-icon>
      </v-btn>
      <v-btn small>
        <span>Participants</span>
        <v-icon>mdi-account-multiple</v-icon>
      </v-btn>
      <v-btn small @click="$nuxt.$emit('openMenuMobile')">
        <span>More</span>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
  </v-bottom-navigation>
</template>

<script>
export default {
  name: "video-bottom-mobile",
  data: () => ({ 
    value: 1,
    blockRoom: false,
    renameNickname: false,
    waitingRoom: false,
    shareScreen: true,
    chat: true,
    
  }),
}
</script>

<style lang="scss">
  .video-mobile {

    &__menu-bottom {
      display: flex;
      align-items: center;
      justify-content: space-between !important;
      background-color: #1E1E1E !important;
      height: 56px;
    }

    .v-btn {
      min-width:auto !important;
      &__content {
        font-size: 10px;
      }
    }
  }
</style>