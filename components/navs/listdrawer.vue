<template>
  <v-list
      nav
    >
    <v-list-item-group
        active-class=" text--accent-4"
      >
        <v-list-item-group>
          <v-list-item link>
              <a href="tel:+37307966626">
                <v-icon>mdi-phone</v-icon>
                079 66626
              </a>
          </v-list-item>
        </v-list-item-group>

        <v-list-item>
          <v-list-item-title>Bar</v-list-item-title>
        </v-list-item>

        <v-list-item>
          <v-list-item-title>Fizz</v-list-item-title>
        </v-list-item>

        <v-list-item>
          <v-list-item-title>Buzz</v-list-item-title>
        </v-list-item>
      </v-list-item-group>
    </v-list>
</template>


<script>

export default {
      name: "listdrawer",
      data: () => ({
      items: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
    }),
}
</script>
