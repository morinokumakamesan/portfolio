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

export default {
  data() {
    return {
      menus: [
        {
          id: '1',
          src: 'https://3d-cad.s3.amazonaws.com/Radio/%E3%83%A9%E3%82%B7%E3%82%99%E3%82%AA%E6%AD%A3%E9%9D%A2.jpg',
          link: "/3dcads/1"
        },
      ]
    }
  }
}
</script>
