<template>
  <v-app>
    <v-app-bar :clipped-left="clipped" fixed app height="90">
      <div class="container">
        <v-row class="d-lg-flex justify-content-between align-center">
          <v-col
            class="d-none"
          >
            <v-app-bar-nav-icon />
          </v-col>
          <v-col
            class="col-3 d-flex justify-start"
          >
            <v-toolbar-title>
              <router-link
                to="/"
                style="text-decoration: none"
              >
                <v-img
                  width="200"
                  :src="require('../assets/img/near-hispano-logo.png')"
                />
              </router-link>
            </v-toolbar-title>
          </v-col>
          <v-col
            class="col-6 d-flex justify-center mt-7"
            align-self="center"
          >
            <v-autocomplete
              v-model="values"
              :items="items"
              outlined
              dense
            />
          </v-col>
          <v-col
            class="col-3 d-flex justify-end"
          >
            <div
              class="text-right"
            >
              <v-btn
                class="ma-2"
                rounded
                outlined
                large
              >
                Conectar Wallet
              </v-btn>
            </div>
          </v-col>
        </v-row>
      </div>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      fixed: false,
      miniVariant: true,
    }
  },
}
</script>
