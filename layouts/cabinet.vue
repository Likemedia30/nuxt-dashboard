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
          </div>
        </div>
      </main>
  </v-app>
</template>


<script>
import NavComponent from '@/components/navs/navbar';
import NavCabinet from '@/components/navs/nav-cabinet';
export default {
  name: "cabinet-loyout",
  components: {
    NavComponent,
    NavCabinet
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