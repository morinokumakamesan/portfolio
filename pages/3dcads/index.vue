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
            ></v-img>
          </v-card>
        </v-hover>
      </NuxtLink>
    </v-flex>
  </v-layout>
</template>

<script>

export default {
  data() {
    return {
      menus: [
        {
          id: '1',
          src: require("../../assets/3dcads/radio/front.jpg"),
          link: "/3dcads/1"
        },
        {
          id: '2',
          src: require("../../assets/3dcads/kokuyo2019/1.png"),
          link: "/3dcads/2"
        },
      ]
    }
  }
}
</script>
