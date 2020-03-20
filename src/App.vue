<template>
  <v-app>
    <v-content>
       <v-navigation-drawer permanent v-show="!mostra"> 
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="title">
                Application
              </v-list-item-title>
              <v-list-item-subtitle>
                subtext
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-divider></v-divider>

          <v-list
            dense
            nav
          >
            <v-list-item
              v-for="item in items"
              :key="item.title"
              link
            >
              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
          <v-container>
          <v-layout justify-center>
            <v-btn
              color="pink"
              dark
              @click.stop="mostra = !mostra"
            >
              Mostra
            </v-btn>
          </v-layout>
        </v-container>
            </v-navigation-drawer>
      <Home v-show="mostra"/>
    </v-content>
  </v-app>
</template>

<script>
import Home from "./components/Home";

export default {
  name: "App",

  components: {
    Home
  },

  data: () => ({
    items: [
      { title: 'Java' },
      { title: 'Kotlin'},
      { title: 'JavaScript' },
    ],
    mostra:false
  }),
};
</script>
