<template>
  <v-layout
    row
    wrap
  >
    <v-flex
      xs12
      v-for="(profile, i) in profiles"
      :key="i"
      mt-5
      mb-2
    >
      <v-layout
        wrap
        align-center
      >
        <v-flex
          sm2
          xs12
          offset-sm2
        >
          <v-card flat color="grey lighten-3">
            <v-card-text class="title font-weight-bold">{{ profile.title }}</v-card-text>
          </v-card>
        </v-flex>
        <v-flex
          sm6
          xs12
        >
          <v-card flat color="grey lighten-3" style="white-space:normal; word-wrap:break-word;">
            <v-card-text class="content" v-if="profile.contact">{{ profile.content_1 }} <br><br> hoge</v-card-text>
            <v-card-text class="content" v-else>
              {{ profile.content_1 }}
              <br>
              {{ profile.content_2 }}
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-flex>

    <!-- <v-flex xs6 offset-xs5 offset-md2 offset-lg5>
      <v-card dark color="secondary">
        <v-card-text>xs7 offset-(xs5 | md2 | lg5)</v-card-text>
      </v-card>
    </v-flex>
    <v-flex xs12 sm5 md3>
      <v-card dark color="primary">
        <v-card-text>(xs12 | sm5 | md3)</v-card-text>
      </v-card>
    </v-flex> -->
  </v-layout>
</template>
<script>
export default {
  data() {
    return {
      profiles: [
        {
          title: 'about',
          content_1: `熊本育ち.`,
          content_2: `現在IoTスマートホームの商用化に携わりながら，趣味で3DCADを触っています．`,
          contact: false
        },
        {
          title: 'skill',
          content_1: `HTML, CSS, Vue, Nuxt, JQuery, Ruby, Rails, Python, XD, Fusion360`,
          content_2: "",
          contact: false
        },
        {
          title: 'contact',
          content_1: `morinokumakamesan[at]gmail.com`,
          content_2: "",
          contact: true
        },
      ]
    }
  }
}
</script>
<style lang="scss">
.content {
  font-size: 18px;
}
</style>
