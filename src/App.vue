<template>
  <v-app>
    <v-app-bar app color="primary">
      <v-col cols=2>
        <v-toolbar-title @click="goHome()" class="display-2 font-weight-black">Term</v-toolbar-title>

      </v-col>
      <v-col cols=8>
          <v-spacer></v-spacer>
      </v-col>
      <v-col  class="my-12" cols=2>
        <v-select
            :items="dropdown_font"
            segmented
            hide-details

            label="Language"
            target="#dropdown-example-2"
        ></v-select>
      </v-col>
    </v-app-bar>

    <v-main>
      <transition>
        <router-view></router-view>
      </transition>
    </v-main>
    <v-footer>
      <v-spacer></v-spacer>
      <div>
        {{ new Date().getFullYear() }} &copy; <a href="https://github.com/zy84338719" target="_blank">murphyyi.com</a>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    dropdown_font: [
      { text: 'CN' },
      { text: 'EN' },
      { text: 'BR' },
      { text: 'ZH_TW' },
    ],
    //
  }),

  created: function() {},
  methods: {
    goHome() {
      if(this.$router.currentRoute.fullPath === "/"){
        return
      }
      this.$router.replace("/");
    },
  },
};
</script>
