<template>
  <v-app light style="background: #EEEEEE">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      :right="right"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <!-- 画面サイズsm以下時のヘッダー -->
    <v-toolbar
      :clipped-left="clipped"
      color="grey lighten-3"
      fixed
      flat
      app
      class="hidden-md-and-up"
    >
      <v-toolbar-title @click="goHome" v-text="title"/>
      <v-spacer />
      <v-btn
        icon
        @click.stop="drawer = !drawer"
        class="hidden-md-and-up"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>

    <!-- 画面サイズmd以上時のヘッダー -->
    <v-toolbar
      :clipped-left="clipped"
      color="grey lighten-3"
      fixed
      flat
      app
      extended
      class="hidden-sm-and-down"
    >
      <v-layout row justify-center>
        <!-- <v-toolbar-title class="headline" @click="goHome" v-text="title"/> -->
        <v-toolbar-title class="bar" @click="goHome" v-text="title"/>
      </v-layout>
      <template #extension>
        <v-layout row justify-center>
          <v-btn 
            v-for="(btn, i) in btns"
            :key="i"
            :to="btn.to"
            color="teal darken-1"
            router
            flat
            exact
            outline
          >
          {{ btn.title }}
          </v-btn>
        </v-layout>
      </template>
    </v-toolbar>


    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer
      :fixed="fixed"
      app
      color="grey lighten-2"
    >
      <v-layout justify-center>
        <span>&copy; 2019 morinokumakamesan</span>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'home',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'person',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'apps',
          title: 'Apps',
          to: '/apps'
        },
        {
          icon: 'format_paint',
          title: '3DCADs',
          to: '/3dcads'
        }
      ],
      btns: [
        {
          title: 'Home',
          to: '/'
        },
        {
          title: 'about',
          to: '/about'
        },
        {
          title: 'apps',
          to: '/apps'
        },
        {
          title: '3dcads',
          to: '/3dcads'
        }
      ],
      miniVariant: false,
      right: false,
      title: 'Eiji Kumakawa'
    }
  },
  methods: {
    goHome() {
      this.$router.push('/')
    }
  }
}
</script>

<style scoped>
.bar {
  font-size: 30px;
  font-family: 'Muli', sans-serif;
  cursor: pointer;
}
</style>