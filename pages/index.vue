<template>
  <v-layout
    justify-space-around
    align-center
  >
    <v-flex
      xs12
      sm12
      md12
    >
      <div class="text-xs-center">
        <logo />
        <p class="title" style="margin: 2% 0 0%; color: gray;">Web Engineering & Design</p>
        <v-btn icon style="margin: 1% 0 3%" href="https://github.com/morinokumakamesan"><v-icon>fab fa-github</v-icon></v-btn>
      </div>
      <v-layout
        row
        justify-center
        align-center
        wrap
      >
        <v-flex
          v-for="(menu, i) in menus"
          :key="i"
          xs12
          sm6
          md4
          pb-4
          mx-4
          justify-center
        >
          <NuxtLink :to="menu.link" style="text-decoration: none;">
            <v-hover>
              <v-card
                slot-scope="{ hover }"
                :class="`elevation-${hover ? 12 : 2}`"
                class="mx-auto"
                width="100%"
              >
                <v-img
                  :src="menu.src"
                  :class="menu.class"
                >
                  <v-card-title
                    v-text="menu.title"
                    class="fill-height align-end headline"
                  >
                  </v-card-title>
                </v-img>
              </v-card>
            </v-hover>
          </NuxtLink>
        </v-flex>
      </v-layout>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo,
  },
  data() {
    return {
      menus: [
        {
          title: 'APPs',
          src: require("../assets/apps.png"),
          link: "/apps",
          class: "white--text"
        },
        {
          title: '3DCAD',
          src: require("../assets/3dcads.png"),
          link: "3dcads",
          class: "black--text"
        },
      ]
    }
  }
}
</script>
