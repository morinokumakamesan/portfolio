<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      v-for="(app, i) in apps"
      :key="i"
      xs12
      md4
      mx-4
    >
      <v-card
        class="mx-auto"
        max-width="400"
        outline
      >
        <v-img
          height="200px"
          :src='app.src'
        />
        <v-flex
          px-3
          pt-3
        >
          <span class="grey--text text--darken-1">{{ app.year }}</span><br>
          <a class="headline" :class='app.class' pb-20 :href="app.to" style="text-decoration: none;">{{ app.title }}</a>
          <v-btn icon style="margin: 1% 0 3%" :href="app.github"><v-icon size="20px">fab fa-github</v-icon></v-btn>
        </v-flex>

        <v-card-text style="white-space:pre-line; word-wrap:break-word;">
          <span class="text--primary">
            <span>{{ app.content }}</span>
          </span>
        </v-card-text>

        <v-flex
          px-3
          pb-1
        >
          <v-layout class="align-center" wrap>
            <v-icon size="20px">fas fa-key</v-icon>
            <span style="padding: 0px 0px 0px 8px"> ： </span>
            <v-chip
              v-for="(chip, i) in app.chips"
              :key="i"
              class="ma-2"
              :color="chip.color"
              outlined
              text-color="white"
            >
              {{ chip.title }}
            </v-chip>
          </v-layout>
        </v-flex>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      apps: [
        {
          title: 'portfolio',
          year: '2019/08',
          content: `当ポートフォリオです．
          `,
          class: 'green--text text--darken-2',
          pos: 'fill-height', //下：'fill-height'
          src: require('../assets/apps/portfolio.png'),
          to: 'https://morinokumakamesan.netlify.com',
          github: 'https://github.com/morinokumakamesan/portfolio',
          chips: [
            {
              title: 'Nuxt.js',
              color: 'green'
            },
          ],
        },
        {
          title: '忘年会クイズアプリ',
          year: '2019/12',
          content: `100人規模の部署忘年会で使用しました．
          `,
          class: 'green--text text--darken-2',
          pos: 'fill-height', //下：'fill-height'
          src: require('../assets/apps/quiz.png'),
          to: 'https://quiz-si-2019.herokuapp.com/',
          github: 'https://github.com/yuzukuma/Quiz',
          chips: [
            {
              title: 'Nuxt.js',
              color: 'green'
            },
            {
              title: 'Node.js',
              color: 'light-green'
            },
            {
              title: 'socket.io',
              color: 'cyan'
            },
          ],
        },
      ]
    }
  }
}
</script>
