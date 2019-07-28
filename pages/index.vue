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
        <p>morinokumakamesan</p>
      </div>
      <v-flex
        pb-4
      >
        <v-card
          flat
        >
          <v-card-text>
            Webやデザイン，データサイエンスに興味があります
          </v-card-text>
        </v-card>
      </v-flex>
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
        >
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
          title: 'web',
          src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        },
        {
          title: 'data science',
          src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        },
        {
          title: 'CAD',
          src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        },
      ]
    }
  }
}
</script>
