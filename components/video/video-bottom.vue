<template>
  <v-bottom-navigation
    class="video__menu-bottom"
    :value="value"
    color="primary"
    dark
  > 
    <v-sheet dark>
      <v-btn>
        <span>Microphone</span>
        <v-icon>mdi-microphone</v-icon>
      </v-btn>

      <v-btn>
        <span>Camera</span>
        <v-icon>mdi-film</v-icon>
      </v-btn>
    </v-sheet>
    <v-sheet dark>
      <v-menu
        
        top
        offset-y
        dark
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn v-bind="attrs"
            v-on="on">
            <span>Security</span>
            <v-icon>mdi-security</v-icon>
          </v-btn>
        </template>
        <v-list dense
          class="securityMenu"
        >
          <v-list-item>
            <v-list-item-title>
              <v-checkbox
              dark
              v-model="blockRoom"
              label="Block this room"
              value="blockRoom"
              hide-details
            ></v-checkbox>
            </v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>
              <v-checkbox
              dark
              v-model="waitingRoom"
              label="ON waiting room"
              value="waitingRoom"
              hide-details
            ></v-checkbox>
              
            </v-list-item-title>
          </v-list-item>
          <v-divider class="my-3"></v-divider>
          <v-list-item>
            <v-list-item-title>
              <v-checkbox
              dark
              v-model="shareScreen"
              label="Share Screen"
              value="shareScreen"
              hide-details
            ></v-checkbox>
            </v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>
              <v-checkbox
              dark
              v-model="chat"
              label="Chat"
              value="Chat"
              hide-details
            ></v-checkbox>
              
            </v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>
              <v-checkbox
              dark
              v-model="renameNickname"
              label="Rename nickname"
              value="renameNicname"
              hide-details
            ></v-checkbox>
              
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn>
        <span>Participants</span>
        <v-icon>mdi-account-multiple</v-icon>
      </v-btn>

      <v-btn @click="$nuxt.$emit('openChat')">
        <span>Chat</span>
        <v-icon>mdi-chat</v-icon>
      </v-btn>
      <v-btn>
        <span>Share Screen</span>
        <v-icon>mdi-monitor-share</v-icon>
      </v-btn>
      <v-btn>
        <span>Record</span>
        <v-icon>mdi-radiobox-marked</v-icon>
      </v-btn>
      <v-btn>
        <span>Reactions</span>
        <v-icon>mdi-emoticon</v-icon>
      </v-btn>
    </v-sheet>
    <v-sheet dark class="but-end">
      <v-btn height="36" dark  color="secondary">
        End
      </v-btn>
    </v-sheet>
  </v-bottom-navigation>
</template>

<script>
export default {
  name: "video-bottom",
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
  .video {

    &__menu-bottom {
      display: flex;
      align-items: center;
      justify-content: space-between !important;
      background-color: #1E1E1E !important;
    }

    .v-sheet {
      height: 56px;
      display: flex;
      align-items: center;
    }

    .but-end {
      padding-right: 15px;
      padding-left: 15px;

      .v-btn span {
        color: #ffff
      }
    }
  }
  .securityMenu {
    .v-input--selection-controls__input:hover {

      .v-input--selection-controls__ripple {
        display: none;
      }
    }
    .mdi-checkbox-marked::before {
      content: "\F012C" !important;
    }
    .mdi-checkbox-blank-outline::before {
      content: "" !important;
    }
  }
</style>