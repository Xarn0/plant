<template>
  <div height="610">
    <v-row class="justify-center d-none d-md-flex" dense>
      <v-col cols="5">
        <v-img width="610" style="margin-top: -64px">
          <img src="@/assets/img/headerimg.jpg" id="home" alt="" />
        </v-img>
      </v-col>
      <v-col cols="7">
        <v-row class="justify-center" style="height: 103%">
          <v-col xs="8" lg="8" justify-center align-self="end" align-center
            ><h4
              class="d-flex justify-center align-center mb-7"
              :style="styleTitle"
            >
              Kembang Flower Mantap
            </h4>

            <p>
              Lorem Ipsum is simply dummy text of the printing and typesetting
              industry. Lorem Ipsum has been the industry's standard dummy text
              ever since the 1500s,
            </p></v-col
          >
          <v-col
            offset="2"
            class="d-flex align-end"
            align-self="end"
            height="100%"
          >
            <v-btn
              class="HeaderBtn justify-start text-left transparent elevation-0"
              height="160"
            >
              <div class="d-block">
                <p class="HeaderBtn__title">
                  <v-icon class="pr-1">mdi-arrow-left</v-icon>Previous
                </p>
                <br />
                <p
                  class="text-capitalize font-weight-medium HeaderBtn__content"
                  style="color: #156963"
                >
                  Kaktus Plant
                </p>
              </div>
            </v-btn>
            <v-btn
              color="#156963"
              class="HeaderBtn text-left justify-start"
              height="160"
            >
              <div class="pl-2">
                <p class="HeaderBtn__title" color="" style="color: #f2f2f2">
                  next<v-icon class="pl-1">mdi-arrow-right</v-icon>
                </p>
                <br />
                <p
                  class="text-capitalize font-weight-medium white--text HeaderBtn__content"
                >
                  Kaktus Plant
                </p>
              </div>
            </v-btn>
          </v-col></v-row
        >
      </v-col>
    </v-row>
    <v-container>
      <v-row class="mt-16">
        <v-col cols="12">
          <v-row class="servisesContent">
            <template v-for="(element, i) in listServises">
              <v-col cols="12" sm="6" md="3" tag="div" :key="i">
                <v-hover
                  v-slot="{ hover, prop }"
                  open-delay="23"
                  close-delay="123"
                >
                  <v-card
                    v-bind="prop"
                    style="border: 2px solid #e0e0e0"
                    :color="hover ? '#e6e2e3' : undefined"
                  >
                    <v-row class="pa-6">
                      <v-col cols="12">
                        <v-row class="flex-rows">
                          <v-col cols="3"
                            ><v-img
                              :src="
                                require(`~/assets/icons/${element.icon}.svg`)
                              "
                            ></v-img
                          ></v-col>
                          <v-col cols="7" class="pl-3">
                            <p
                              v-if="checkLen(element.title)"
                              class="servisesContent__title servisesContent__title-bigtext"
                            >
                              {{ element.title }}
                            </p>

                            <p
                              v-else
                              style="color: #156963"
                              class="font-weight-bold text-subtitle servisesContent__title"
                            >
                              {{ element.title }}
                            </p></v-col
                          >
                        </v-row>
                      </v-col>
                      <v-col cols="12"
                        >Lorem ipsum dolor sit amet consectetur adipisicing
                        elit. Porro saepe eum eaque dignissimos</v-col
                      >
                    </v-row>
                  </v-card></v-hover
                ></v-col
              >
            </template>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <v-row>
        <v-col cols="12">
          <v-row class="pb-5">
            <v-col class="align-self-end"
              ><p class="text-h5 font-weight-medium">Featured Plants</p></v-col
            >
            <v-col cols="3" class="justify-end d-flex">
              <v-autocomplete
                dense
                solo
                hide-details="true"
                append-icon="mdi-chevron-down"
              ></v-autocomplete
            ></v-col>
          </v-row>
          <v-divider></v-divider>

          <v-col cols="12" lg="11" class="pa-0">
            <v-list
              class="d-flex list flex-wrap flex-lg-nowrap justify-sm-space-between justify-center"
              dense
            >
              <v-card
                flat
                v-for="(el, i) in listFlowers"
                :key="i"
                class="pa-2"
                style="width: 217px"
              >
                <v-row>
                  <v-col cols="12" class="d-flex align-center">
                    <v-img
                      width="217px"
                      :src="require(`@/assets/img/flowers/flower${i + 1}.png`)"
                      alt="2"
                    />
                  </v-col>
                  <v-col cols="12" class="text-center">
                    <h3>{{ el.title }}</h3>
                    <p>IDR {{ el.price }}</p>
                  </v-col>
                </v-row></v-card
              >
            </v-list>
          </v-col>
        </v-col>
      </v-row>
      <v-row class="justify-center justtify-md-start my-10">
        <v-col cols="12" md="6">
          <v-row class="align-items-center" style="height: 100%">
            <v-col cols="12" md="10"
              ><h4
                class="font-weight-bold mb-8"
                style="font-size: 44px; line-height: 1.2"
              >
                Buy more plants, it helps you to be relaxed
              </h4>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi
                gravida gravida aliquam. Pellentesque et lobortis nisl. Sed et
                mauris justo. Nulla eu enim non mauris maximus dignissim.
                Maecenas vitae eros sapien. Quisque pellentesque tempus
                dignissim.
              </p></v-col
            >
            <v-col
              cols="12"
              md="11"
              align-self="end"
              class="pa-0"
              style="margin-top: 10px"
            >
              <img
                src="@/assets/img/background2.jpg"
                alt="838"
                style="width: 100%"
                aspect-ratio=""
              />
            </v-col>
          </v-row>
        </v-col>
        <v-col md="6" class="pa-0 pl-3 pb-6 d-none d-md-block">
          <img
            src="@/assets/img/background.jpg"
            alt="img"
            style="width: 100%"
          />
        </v-col>
      </v-row>
      <v-row
        ><v-col cols="12" class="pl-0 pr-0"
          ><div style="background: #f3f4f6" class="pa-16 pr-4 pb-0">
            <v-row class="flex-column flex-sm-row">
              <v-col cols="6" class="pl-7 flex-column"
                ><h3 style="line-height: 1.2" class="mb-10 mt-7 text--md-h3">
                  Get your favourites plant on our shop now
                </h3>
                <v-btn
                  color="#156963"
                  class="white--text text-body-2 text-capitalize"
                  style="letter-spacing: 1.2px"
                  @click="$vuetify.goTo('#home')"
                  >Visit Shop</v-btn
                ></v-col
              >
              <v-col cols="6" class="pa-0 d-flex justify-end">
                <img
                  class="pb-0"
                  style="max-width: 100%"
                  src="@/assets/img/background3.png"
                  alt=""
                />
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "blog",
  data() {
    return {
      selectItem: false,
      styleTitle: [
        {
          "font-size": "68px",
          "font-weight": "500",

          color: "#156963",
          "font-family": "Montserrat",
          "line-Height": "70px",
        },
      ],
      listServises: [
        { icon: "fastdelivery", title: "Fast Delivery" },
        { icon: "headphones", title: "Great Customer " },
        { icon: "plant", title: "Original Plants" },
        { icon: "dollar-symbol", title: "Affordable Price" },
      ],
      listFlowers: [
        {
          img: "",
          title: "Kaktus Plants",
          price: 85.0,
        },
        {
          img: "",
          title: "Landak Plants",
          price: 105.0,
        },
        {
          img: "",
          title: "Kecubung Plants",
          price: 85.0,
        },
        {
          img: "",
          title: "Kecubung Plants",
          price: 85.0,
        },
        {
          img: "",
          title: "Kecubung Plants",
          price: 85.0,
        },
      ],
    };
  },
  methods: {
    checkLen(title) {
      if (title.length > 17) {
        return true;
      }
      return false;
    },
  },
};
</script>

<style lang="scss">
.HeaderBtn {
  /* display: block;/ */
  /* height:50%; */
  justify-content: baseline;
  width: 50%;
  &__title {
    font-size: 24px;
    color: hsla(0, 0%, 95%, 1);
    display: flex;
    align-items: center;
  }
  &__content {
    font-size: 32px;
  }
}
p {
  margin: 0;
}
.servisesContent {
  &__title {
    font-family: "Montserrat";
    font-size: 18px;
    // font-size: 24px;
    &-bigtext {
      font-size: 16px;
      font-weight: bold;
      color: #156963;
      overflow: hidden;
    }
  }
}
.select {
  width: 130px;
  border: 1px solid #940;
  padding: 0 15px;
  text-align: center;
  position: relative;
  display: flex;
  cursor: pointer;
  ul {
    display: none;
    margin-top: 20px;
  }
  &::after {
    content: "\\/";
    // width: 90px;
    // height: 90px;
    // position: absolute;
    // background: #444;
    margin-left: auto;
  }
}
.select.active {
  ul {
    display: block;
  }
  &::after {
    content: "/\\";
  }
}
</style>
