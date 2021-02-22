<template>
  <div class="row cabinet-content">
    <div class="col-lg-10 col-md-12 col-12 display-1 text-center my-5">
      Comenzile mele
    </div>
    <div v-for="(item, i) in 10" :key="i" class="col-xl-4 col-lg-6 col-md-8 col-sm-10 col-12">
      <card-order />
    </div>
  </div>
</template>

<script>
import CardOrder from '@/components/widgets/card/CardOrder'
export default {
  layout: "cabinet",
  components: {
    CardOrder
  },
  data: () => ({

  }),
}
</script>

<style lang="scss">

</style>
