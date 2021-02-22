<template>
  <v-app id="root">
    <NavComponent></NavComponent>
      <main>
        <div class="container">
          <div class="row">
            <div class="col-auto pad">
              <nav-cabinet></nav-cabinet>
            </div>
            <div class="col">
              <nuxt />
            </div>
            <div class="col-12">
              <support />
            </div>
            <div class="col-12">
              <count />
            </div>
          </div>
        </div>
      </main>
    <Footer />
  </v-app>
</template>


<script>
import NavComponent from '@/components/navs/navbar';
import NavCabinet from '@/components/navs/nav-cabinet';
import Support from '@/components/blocs/support';
import Count from '@/components/blocs/count';
import Footer from '@/components/navs/Footer'

export default {
  name: "cabinet-loyout",
  components: {
    NavComponent,
    NavCabinet,
    Support,
    Count,
    Footer
  }
}
</script>

<style lang="scss">
  .pad {
    padding: 0;
  }
  @media (min-width: 992px) {
      
      .pad {
        padding: 0 15px;
      }
  }
</style>