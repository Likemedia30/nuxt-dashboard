<template>
  <main>
    <div id="pageTable">
    <v-container grid-list-xl fluid>
      <v-layout row wrap>
        <v-flex lg12>
          <v-card>
            <v-toolbar flat color="white">
              <v-text-field
                flat
                solo
                prepend-icon="mdi-magnify"
                placeholder="Type something"
                v-model="search"
                hide-details
                class="hidden-sm-and-down"
              ></v-text-field>
              <v-btn icon>
                <v-icon>mdi-filter</v-icon>
              </v-btn>
            </v-toolbar>
            <v-divider></v-divider>
            <v-card-text class="pa-0">
              <v-data-table
                :headers="complex.headers"
                :search="search"
                :items="complex.items"
                class="elevation-1"
                item-key="name"
                show-select
                v-model="selected"
              >
              
                <template v-slot:[`item`]="{ item }">
                  <tr>
                    <td>
                    <v-checkbox
                      primary
                      hide-details
                      v-model="selected"
                    ></v-checkbox>
                  </td>
                  <td>
                    <v-avatar size="32">
                      <img :src="item.avatar" alt="">
                    </v-avatar>
                  </td>
                  <td>
                    <span>{{ item.name }}</span>
                    <span>{{ item.email }}</span>
                  </td>
                  <td>
                    <span>Functia: {{ item.func }}</span>
                    <span>Rol: {{ item.rol }}</span>
                  </td>
                  <td>
                    <v-btn depressed outlined icon fab dark color="primary" small>
                      <v-icon>mdi-pencil</v-icon>
                    </v-btn>
                  </td>
                  <td>
                    <v-btn  outlined  fab dark color="primary" small>
                      <v-icon>mdi-link</v-icon>
                    </v-btn>
                  </td>
                  <td>
                    <v-btn  outlined  fab dark color="primary" small>
                      <v-icon>mdi-calendar</v-icon>
                    </v-btn>
                  </td>
                  <td>
                    <v-btn  outlined  fab dark color="primary" small>
                      <v-icon>mdi-phone</v-icon>
                    </v-btn>
                  </td>
                  <td>
                    <v-btn  outlined  fab dark color="primary" small>
                      <v-icon>mdi-mail</v-icon>
                    </v-btn>
                  </td>
                  <td>
                    <v-btn depressed outlined icon fab dark color="pink" small>
                      <v-icon>mdi-delete</v-icon>
                    </v-btn>
                  </td>
                  </tr>
                </template>
              </v-data-table>
            </v-card-text>
          </v-card>
        </v-flex>

      </v-layout>
    </v-container>
  </div>
  </main>
</template>

<script>
import {Items as Users} from '@/api/user';

  export default {
    layout: "dashboard",
        data() {
        return {
          search: '',
          selected: [],
          complex: {
            
            headers: [
              {
                text: 'Avatar',
                value: 'avatar'
              },
              {
                text: 'Info',
                value: 'info'
              },
              {
                text: 'Role',
                value: 'role'
              },
              {
                text: 'Edit',
                value: 'edit'
              },
              {
                text: 'Copy Link',
                value: 'link'
              },
              {
                text: 'Event',
                value: 'event'
              },
              {
                text: 'Call',
                value: 'call'
              },
              {
                text: 'Message',
                value: 'message'
              },
              {
                text: 'Delete',
                value: 'delete'
              }
            ],
            items: Users
          },
          basic: {
            headers: [
              {
                text: 'Dessert (100g serving)',
                align: 'left',
                sortable: false,
                value: 'name'
              },
              {text: 'Calories', value: 'calories'},
              {text: 'Fat (g)', value: 'fat'},
              {text: 'Carbs (g)', value: 'carbs'},
              {text: 'Protein (g)', value: 'protein'},
              {text: 'Iron (%)', value: 'iron'}
            ],
            items: [
              {
                value: false,
                name: 'Frozen Yogurt',
                calories: 159,
                fat: 6.0,
                carbs: 24,
                protein: 4.0,
                iron: '1%'
              },
              {
                value: false,
                name: 'Ice cream sandwich',
                calories: 237,
                fat: 9.0,
                carbs: 37,
                protein: 4.3,
                iron: '1%'
              },
              {
                value: false,
                name: 'Eclair',
                calories: 262,
                fat: 16.0,
                carbs: 23,
                protein: 6.0,
                iron: '7%'
              },
              {
                value: false,
                name: 'Cupcake',
                calories: 305,
                fat: 3.7,
                carbs: 67,
                protein: 4.3,
                iron: '8%'
              },
              {
                value: false,
                name: 'Gingerbread',
                calories: 356,
                fat: 16.0,
                carbs: 49,
                protein: 3.9,
                iron: '16%'
              },
              {
                value: false,
                name: 'Jelly bean',
                calories: 375,
                fat: 0.0,
                carbs: 94,
                protein: 0.0,
                iron: '0%'
              },
              {
                value: false,
                name: 'Lollipop',
                calories: 392,
                fat: 0.2,
                carbs: 98,
                protein: 0,
                iron: '2%'
              },
              {
                value: false,
                name: 'Honeycomb',
                calories: 408,
                fat: 3.2,
                carbs: 87,
                protein: 6.5,
                iron: '45%'
              },
              {
                value: false,
                name: 'Donut',
                calories: 452,
                fat: 25.0,
                carbs: 51,
                protein: 4.9,
                iron: '22%'
              },
              {
                value: false,
                name: 'KitKat',
                calories: 518,
                fat: 26.0,
                carbs: 65,
                protein: 7,
                iron: '6%'
              }
            ]
          }
        };
    }
  }
</script>

<style scoped>
  td span,
  thead {
    display: block;
    font-size: 14px !important;
  }
  .v-input--selection-controls {
    margin-top: 0 !important;
    padding-top: 0 !important;
  }
</style>
