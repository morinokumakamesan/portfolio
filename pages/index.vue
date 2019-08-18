<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm12
      md12
    >
      <div class="text-xs-center">
        <logo />
        <p class="title" style="margin: 2% 0 6%">morinokumakamesan</p>
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
          justify-center
        >
          <NuxtLink :to="menu.link" style="text-decoration: none;">
            <v-hover>
              <v-card
                slot-scope="{ hover }"
                :class="`elevation-${hover ? 12 : 2}`"
                class="mx-auto"
                width="80%"
              >
                <v-img
                  :src="menu.src"
                ></v-img>
                <v-card-title>
                  <div>
                    <span class="headline">{{ menu.title }}</span>
                  </div>
                  <v-spacer />
                  <v-btn icon class="mr-0">
                    <v-icon>mdi-chevron-right</v-icon>
                  </v-btn>
                </v-card-title>
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
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      menus: [
        {
          title: 'app',
          src: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          link: "/app"
        },
        {
          title: '3DCAD',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
          link: "3dcads"
        },
      ]
    }
  }
}
</script>
