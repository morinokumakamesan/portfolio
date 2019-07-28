<template>
  <v-app light style="background: #F5F5F5">
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
      color="grey lighten-4"
      fixed
      flat
      app
      class="hidden-md-and-up"
    >
      <v-toolbar-title v-text="title"/>
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
      color="grey lighten-4"
      fixed
      flat
      app
      dense
      extended
      class="hidden-sm-and-down"
    >
    <v-layout row justify-center>
      <v-toolbar-title v-text="title"/>
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
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>
              compare_arrows
            </v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :fixed="fixed"
      app
      color="grey lighten-3"
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
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
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
          title: 'web',
          to: '/web'
        },
        {
          title: 'Data Science',
          to: '/data_science'
        },
        {
          title: 'cad',
          to: '/3dcads'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'kame\'s portfolio'
    }
  }
}
</script>
