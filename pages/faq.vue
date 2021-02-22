<template>
  <div class="container">
    <div class="row faq-content">
      <div class="col-12">
        <v-title class="display-1 text-center">
          General account management
        </v-title>
      </div>
      <div class="col-12">
        <div class="v-list">
          <v-list-item v-for="(item, i) in items" :key="i" exact nuxt to="/faq-one" >
            <v-list-item-text>
              {{item}}
            </v-list-item-text>
          </v-list-item>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      "Known Issues",
      "Referral Program",
      "Why was my account disabled?",
      "Buyer FAQs",
      "How Tienda Works",
      "How Do I Change My Username?",
      "Account and profile settings",
      "How do I change my email?",
      "Closing my Tienda account",
      "Permanently deleting my account",
      "Warnings",
      "Searching Your History"
    ]
  })
}
</script>

<style scoped>
  .faq-content {
    padding-top: 56px;
  }
  @media (min-width: 991px) {
    .faq-content {
      padding-top: 150px;
    }
  }
</style>