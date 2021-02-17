  <template>
  <v-container>
    <v-layout row class="align-center layout px-4 pt-4 app--page-header">
    <div class=" page-header-left">
      <h5 class="pr-3">{{title}}</h5>
    </div>
    <v-icon>mdi-home</v-icon>
    <v-breadcrumbs class="" divider="--" :items="breadcrumbs">

    </v-breadcrumbs>
    <v-spacer class=""></v-spacer>
    <div class=" page-header-right">
      <v-btn icon>
        <v-icon class="text--secondary">mdi-refresh</v-icon>
      </v-btn>
    </div>
  </v-layout>  
  </v-container>
</template>

<script>
import menu from '@/api/menu';
export default {
  data () {
    return {
      title: ''
    };
  },
  computed: {
    breadcrumbs: function () {
      let breadcrumbs = [];
      menu.forEach(item => {
        if (item.items) {
          let child =  item.items.find(i => {
            return i.href === this.$route.path;
          });
          if (child) {
            breadcrumbs.push({text: item.title});
            breadcrumbs.push({text: child.title, disabled: true});
            this.title = child.title;
          }
        } else {
          if (item.href === this.$route.path) {
            this.title = item.title;
            breadcrumbs.push({text: item.title});
          }
        }
      });
      return breadcrumbs;
    },    
  }
};
</script>
<style scoped>
  .app--page-header {
    padding-top: 70px !important;
    display: none;
  }
  .theme--dark.v-input {
    height: 47px;
  }
  .v-application ul, .v-application ol {
    padding-left: 20px;
  }

</style>