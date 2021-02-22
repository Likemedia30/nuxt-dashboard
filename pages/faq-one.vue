<template>
  <div class="container">
    <div class="row faq-content">
      <div class="col-12">
        <v-title class="display-1 text-center">
          General account management
        </v-title>
      </div>
      <div class="col-lg-3 col-md-4">
        <v-list class="list-faq-one">
          <v-list-item v-for="(item, i) in items" :key="i" exact nuxt to="/faq-one" >
            <v-list-item-text>
              {{item}}
            </v-list-item-text>
          </v-list-item>
        </v-list>
      </div>
      <div class="col-lg-9 col-md-8 col-sm-12">
        <v-expansion-panels accordeon>
          <v-expansion-panel v-for="(item, i) in items" :key="i">
            <v-expansion-panel-header class="font-weight-bold">
              {{item}}
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              <p class="caption">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Id recusandae reiciendis at. Corrupti ratione quidem maxime ducimus tempora, mollitia delectus illo iure molestiae sequi, reiciendis provident id possimus numquam. Corrupti.
              </p>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
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
  .list-faq-one {
    display: flex;
    flex-wrap: none;
    overflow-x: scroll;
  }
  .list-faq-one a {
    white-space: nowrap;
  }
  @media (min-width: 991px) {
    .faq-content {
      padding-top: 150px;
    }
    .list-faq-one {
    display: block;
    overflow: auto;
  }
  .list-faq-one a {
    white-space: normal;
    padding-top: 5px;
    padding-bottom: 5px;
  }
  }
</style>