<template>
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
          </v-card>
        </v-hover>
      </NuxtLink>
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
          link: "/3dcads/1"
        },
        {
          title: '3DCAD',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
          link: "/3dcads/2"
        },
      ]
    }
  }
}
</script>
