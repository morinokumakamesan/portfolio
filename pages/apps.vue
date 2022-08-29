<template>
  <v-layout
    row
    justify-center
    align-center
    wrap
  >
    <v-flex
      v-for="(app, i) in apps"
      :key="i"
      xs12
      sm6
      md4
      pb-4
      mx-4
      justify-center
      class="row"
    >
      <a :href="app.to" style="text-decoration: none;">
      <v-hover>
        <v-card
          slot-scope="{ hover }"
          :class="`elevation-${hover ? 12 : 2}`"
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
            <!-- <a class="headline" :class='app.class' pb-20 :href="app.to" style="text-decoration: none;">{{ app.title }}</a> -->
            <div class="headline" :class='app.class' pb-20>{{ app.title }}</div>
            <v-btn icon style="margin: 1% 0 3%" :href="app.github" v-if="app.github"><v-icon size="20px">fab fa-github</v-icon></v-btn>
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
      </v-hover>
      </a>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      apps: [
        {
          title: 'NocodeBot',
          year: '2021/10',
          content: `Excelでチャットボットを簡単に作成できるサービスをリリース。
          `,
          class: 'green--text text--darken-2',
          pos: 'fill-height', //下：'fill-height'
          src: require('../assets/apps/nocodebot.png'),
          to: 'https://www.nocode-bot.com/',
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
          content: `お手元のスマホから参加できるオールスター感謝祭風のアプリです。
          100人規模の部署忘年会で使用しました。
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
        {
          title: '杉本孔明Official',
          year: '2019/12',
          content: `シンガーソングライターとして活躍する杉本孔明のOfficialサイトを立ち上げました。
          `,
          class: 'green--text text--darken-2',
          pos: 'fill-height',
          src: require('../assets/apps/komei.png'),
          to: 'https://komei-official.netlify.app/',
          github: 'https://github.com/morinokumakamesan/komei-official',
          chips: [
            {
              title: 'Nuxt.js',
              color: 'green'
            },
          ],
        },
        {
          title: 'portfolio',
          year: '2019/08',
          content: `当ポートフォリオです。
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
      ]
    }
  }
}
</script>
<style scoped>
.row {
	align-items: flex-start;
}
</style>