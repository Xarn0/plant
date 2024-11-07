<template>
  <v-app light>
    <v-app-bar
      app
      class="elevation-0 absolute"
      :class="{ transparent: checkTransparent }"
      dense
      tile
      outlined
      hide-on-scroll
      scroll-threshold="55"
    >
      <v-app-bar-nav-icon
        color="#156963"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-btn color=" mx-2" icon><v-icon>mdi-magnify</v-icon></v-btn>
      <v-btn color=" mx-2" icon><v-icon>mdi-basket</v-icon></v-btn>
      <v-btn
        style="color: #156963"
        @click.stop="dialog2 = true"
        class="mx-1 pa-3 px-sm-5 transparent font-weight-bold elevation-0 text-body-2 text-md-body-1"
        >sign up</v-btn
      >
      <v-btn
        color="#156963"
        class="pa-3 px-sm-5 mx-1 opacity white--text elevation-0 text-body-2 text-md-body-1"
        @click.stop="dialog = true"
        >sign in</v-btn
      >
    </v-app-bar>
    <v-navigation-drawer app v-model="drawer">
      <v-layout class="flex-column" style="height: 100%">
        <v-flex cols="12">
          <v-list>
            <v-list-item-group>
              <v-list-item>
                <v-list-item-content> Lorem ipsum </v-list-item-content>
                <v-icon>mdi-account-box-edit-outline</v-icon>
              </v-list-item>
              <v-list-item>
                <v-list-item-content> Lorem ipsum2 </v-list-item-content>
                <v-icon>mdi-access-point</v-icon>
              </v-list-item>
              <v-list-item>
                <v-list-item-content> Lorem ipsum3 </v-list-item-content>
                <v-icon>mdi-home</v-icon>
              </v-list-item>
              <v-list-item>
                <v-list-item-content> Lorem ipsum4 </v-list-item-content>
                <v-icon>mdi-alpha-f-circle-outline</v-icon>
              </v-list-item>
              <v-list-item>
                <v-list-item-content> Lorem ipsum4 </v-list-item-content>
                <v-icon>mdi-alpha-f-circle-outline</v-icon>
              </v-list-item>
              <v-spacer></v-spacer>
            </v-list-item-group>
          </v-list>
          <div class="d-flex justify-center my-5">
            <v-btn
              color="orange"
              class="white--text justify-center"
              @click="drawer = false"
            >
              <h5>закрыть</h5>
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </div>
        </v-flex>
        <v-flex
          class="d-flex align-end justify-center mb-2 flex-wrap flex-md-nowrap"
        >
          <v-btn color="primary" @click.stop="dialog = true">Вход</v-btn>
          <v-btn color="green white--text ml-md-2" @click.stop="dialog2 = true"
            >Регистрация</v-btn
          >
          <!-- <v-btn>выход</v-btn> -->
        </v-flex>
      </v-layout>
    </v-navigation-drawer>
    <v-dialog v-model="dialog" width="500">
      <v-card>
        <v-card-title class="green white--text lighten-2">
          <div class="flex-column d-flex">
            <p class="text-h5">Вход</p>
            <span class="text-body-2"> В аккаунт </span>
          </div>
          <v-spacer />

          <v-icon color="white" @click="dialog = false">mdi-close</v-icon>
        </v-card-title>

        <v-card elevation="0">
          <v-container>
            <v-form>
              <v-text-field :counter="15" label="Name" required></v-text-field>
              <v-text-field
                type="password"
                label="password"
                required
              ></v-text-field> </v-form
          ></v-container>
        </v-card>

        <v-divider></v-divider>
        <v-spacer></v-spacer>
        <v-card-actions class="text-center d-flex justify-center">
          <v-btn color="primary text-h4 " text @click="dialog = false">
            Вход</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog v-model="dialog2" width="500">
      <v-card>
        <v-card-title
          class="text-h5 purple lighten-2 white--text justify-center lighten-2 flex-column"
        >
          Регистрация
        </v-card-title>

        <v-card elevation="0">
          <v-container>
            <v-form>
              <v-text-field :counter="15" label="Name" required></v-text-field>
              <v-text-field
                type="password"
                label="password"
                required
              ></v-text-field>
              <v-text-field
                type="password"
                label="password"
                required
              ></v-text-field> </v-form
          ></v-container>
        </v-card>

        <v-divider></v-divider>
        <v-spacer></v-spacer>
        <v-card-actions class="text-center d-flex justify-center">
          <v-btn color="primary text-h4 " text @click="dialog2 = false">
            Вход</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-main>
      <div class="d-flex mr-md-10" style="gap: 40px">
        <nuxt />
      </div>
    </v-main>
    <footer class="mt-10">
      <v-divider class="pa-4"></v-divider>
      <v-container>
        <v-row class="justify-space-between">
          <v-col cols="6" sm="4" md="4">
            <v-subheader
              class="pa-0 text-uppercase font-weight-medium"
              style="color: #156963; letter-spacing: 3px; font-size: 24px"
              >plantku</v-subheader
            >
            <div>
              <h5
                style="color: #333333; font-size: 18px; letter-spacing: 2px"
                class="mb-2"
              >
                Plantku House
              </h5>
              <p>
                Jl. Laksda Adisucipto No.51, Demangan, Kec. Depok, Kota
                Yogyakarta, Daerah Istimewa Yogyakarta 55282
              </p>
            </div>
          </v-col>
          <v-col cols="6" sm="3" md="2">
            <v-list>
              <v-subheader class="text-h6 font-weight-bold"
                >Perusahaan</v-subheader
              >
              <v-list-item-group>
                <v-list-item>Tentang Kami</v-list-item>
                <v-list-item>Hubungi Kami2</v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>
          <v-col cols="6" md="2">
            <v-list>
              <v-subheader class="text-h6 font-weight-bold">Produk</v-subheader>
              <v-list-item-group>
                <v-list-item>Tanaman</v-list-item>
                <v-list-item>Tanaman Lain</v-list-item>
              </v-list-item-group>
            </v-list>
          </v-col>

          <v-col cols="6" md="3">
            <v-form>
              <v-subheader
                class="pl-0 text-capitalize black--text font-weight-medium text-body-1"
                >Berlangganan Email Kami</v-subheader
              >
              <v-text-field
                outlined
                class="pa-0"
                dense
                tile
                label="Masukan Alamat Email"
                style="border-color: #f2f2f2"
              ></v-text-field>
              <v-btn color="#156963" class="white--text text-capitalize"
                >submit</v-btn
              >
            </v-form>
          </v-col>
        </v-row></v-container
      >
    </footer>
  </v-app>
</template>

<script>
export default {
  name: "blog",
  data() {
    return {
      drawer: false,
      dialog: false,
      dialog2: false,
    };
  },
  computed: {
    checkTransparent() {
      if (document.body.clientWidth < 966) {
        return false;
      } else {
        return true;
      }
    },
  },
};
</script>

<style></style>
