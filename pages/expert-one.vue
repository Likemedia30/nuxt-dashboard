<template>
  <div class="container">
    <div class="row expert-one-content">
      <div class="col-12">
        <v-title class="display-1 text-center">
          Serviciu
        </v-title>
      </div>
      <div class="col-lg-3 col-md-4">
        <v-list class="list-expert-one">
          <v-sheet class="buttons-expert">
            <v-btn small color="primary" outlined>
              discuta acum
            </v-btn>
            <v-btn small color="primary" outlined>
              comanda serviciu
            </v-btn>
          </v-sheet>
          <v-list-item active-class="active-anchor" v-for="(item, i) in items" :key="i" :href="'#' + item.toLowerCase().replace(/ /g,'')" >
            <v-list-item-text>
              {{item}}
            </v-list-item-text>
          </v-list-item>
        </v-list>
      </div>
      <div class="col-md">
        <h3 class="title" id="section1">
          Section 1
        </h3>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora molestiae cum tenetur modi iusto fugit. Porro provident ad delectus excepturi repellat quis minima exercitationem rerum, cum hic labore, sunt dignissimos!
        </p>
        <img src="data:image/jpeg;base64,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" alt="">
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reprehenderit, ipsa!
        </p>

        <h3 class="title" id="section2">
          Section 2
        </h3>
        <v-simple-table height="300px">
          <template v-slot:default>
            <thead>
              <tr>
                <th class="text-left">
                  Name
                </th>
                <th class="text-left">
                  Calories
                </th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="item in desserts"
                :key="item.name"
              >
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam assumenda debitis corrupti veniam est amet cum aut ab, reiciendis error!
        </p>
      </div>
      <div class="col-lg-3 col-md-4 col-sm-12">
        <div class="expert-one-experts">
          <div class="title mb-2">
            Discuta Live
          </div>
          <v-card v-for="(item, i) in 3" :key="i">
            <v-sheet class="pa-3 d-flex align-start">
              <v-avatar>
                <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="jhon">
                <span class="mark"></span>
              </v-avatar>
              <v-card-text class="pa-0 ml-2">
                Natalia Zlata
                <p class="caption">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                </p>
                <v-sheet class="consultation" color="secondary">
                  Free Consultation
                </v-sheet>
              </v-card-text>
            </v-sheet>
            <v-divider class="mb-2 mt-1"></v-divider>
            <v-card-actions>
              <v-btn color="primary" outlined>
                <v-icon>
                  mdi-chat
                </v-icon>
                Message
              </v-btn>
              <v-btn color="primary" outlined>
                <v-icon>
                  mdi-phone
                </v-icon>
                Call
              </v-btn>
              <v-btn color="primary" nuxt exact to="/calendar">
                <v-icon>
                  mdi-book
                </v-icon>
                Programeaza-te
              </v-btn>
            </v-card-actions>
          </v-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      "Section 1",
      "Section 2",
      "Section 3",
      "Section 4",
    ],
    desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
          },
          {
            name: 'Eclair',
            calories: 262,
          },
          {
            name: 'Cupcake',
            calories: 305,
          },
          {
            name: 'Gingerbread',
            calories: 356,
          },
          {
            name: 'Jelly bean',
            calories: 375,
          },
          {
            name: 'Lollipop',
            calories: 392,
          },
          {
            name: 'Honeycomb',
            calories: 408,
          },
          {
            name: 'Donut',
            calories: 452,
          },
          {
            name: 'KitKat',
            calories: 518,
          },
        ]
  })
}
</script>

<style lang="scss" scoped>
  .expert-one-experts .v-card {
    margin-bottom: 30px;
  }
  .expert-one-experts .v-btn {
    margin-bottom: 10px;
  }
  .v-card__actions {
    flex-wrap: wrap;
    justify-content: space-around;
  }
  .consultation {
    background-color: rgba(0, 0, 0, 0.3);
    color: #ffff;
    text-align: center;
  }
  .caption {
    line-height: 1.3;
  }
  .expert-one-content {
    padding-top: 130px;
  }
  .list-expert-one {
    display: flex;
    flex-wrap: nowrap;
    overflow-x: scroll;
    border-bottom: 2px solid rgba(0, 0, 0, 0.3) !important;
    padding: 0;
  }
  .list-expert-one a {
    white-space: nowrap;
  }
  .list-expert-one--active {
    color: $custom_blue;
    font-weight: 700;
  }

  .buttons-expert {
    position: fixed;
    top: 56px;
    left: 0;
    right: 0;
    z-index: 2;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 15px;
  }
  .buttons-expert .v-btn {
    padding: 5px !important;
  }
  @media (min-width: 991px) {
    .expert-one-content {
      padding-top: 150px;
    }
    .list-expert-one {
      display: block;
      overflow: auto;
      border-bottom: 0;
    }
    .list-expert-one a {
      white-space: normal;
      padding-top: 5px;
      padding-bottom: 5px;
    }
    .buttons-expert {
      position: static;
      display: block;

      .v-btn {
        margin-bottom: 10px;
      }
    }
  }
</style>