<template>
    <v-app id="inspire">
        <!--<v-navigation-drawer-->
                <!--v-model="drawerRight"-->
                <!--app-->
                <!--clipped-->
                <!--right-->
        <!--&gt;-->
            <!--<v-list dense>-->
                <!--<v-list-item @click.stop="right = !right">-->
                    <!--<v-list-item-action>-->
                        <!--<v-icon>mdi-exit-to-app</v-icon>-->
                    <!--</v-list-item-action>-->
                    <!--<v-list-item-content>-->
                        <!--<v-list-item-title>Open Temporary Drawer</v-list-item-title>-->
                    <!--</v-list-item-content>-->
                <!--</v-list-item>-->
            <!--</v-list>-->
        <!--</v-navigation-drawer>-->

        <v-app-bar
                app
                clipped-right
                color="blue-grey"
                dark
        >
            <!--<v-app-bar-nav-icon @click.stop="drawer = !drawer" />-->
            <v-toolbar-title>Toolbar</v-toolbar-title>
            <v-spacer />
            <!--<v-app-bar-nav-icon @click.stop="drawerRight = !drawerRight" />-->
        </v-app-bar>

        <!--<v-navigation-drawer-->
                <!--v-model="drawer"-->
                <!--app-->
        <!--&gt;-->
            <!--<v-list dense>-->
                <!--<v-list-item @click.stop="left = !left">-->
                    <!--<v-list-item-action>-->
                        <!--<v-icon>mdi-exit-to-app</v-icon>-->
                    <!--</v-list-item-action>-->
                    <!--<v-list-item-content>-->
                        <!--<v-list-item-title>Open Temporary Drawer</v-list-item-title>-->
                    <!--</v-list-item-content>-->
                <!--</v-list-item>-->
            <!--</v-list>-->
        <!--</v-navigation-drawer>-->

        <!--<v-navigation-drawer-->
                <!--v-model="left"-->
                <!--fixed-->
                <!--temporary-->
        <!--/>-->



        <v-content>
        <v-container
                class="fill-height"
                fluid
        >
            <v-row
                    align="center"
            >
                <v-col class="text-center">
          <h1 v-if="loading"> <v-progress-circular indeterminate/></h1>
          <HelloWorld v-else/>
                </v-col>
            </v-row>
        </v-container>
        </v-content>

        <!--<v-navigation-drawer-->
                <!--v-model="right"-->
                <!--fixed-->
                <!--right-->
                <!--temporary-->
        <!--/>-->

        <v-footer
                app
                color="blue-grey"
                class="white--text"
        >
            <span>Vuetify</span>
            <v-spacer />
            <span>&copy; 2019</span>
        </v-footer>
    </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import store from "./store"
export default {
  name: 'App',
  props: {
    source: String,
  },

  components: {
    HelloWorld,
  },

  data: () => ({
      drawer: null,
      drawerRight: null,
      right: false,
      left: false,
  }),
  computed: {
      loading () {
          return store.getters.getLoading
      },

  },
};
</script>
