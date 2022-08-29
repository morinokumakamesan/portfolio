<template>
  <v-layout
    row
    wrap
  >
    <v-flex
      xs12
      v-for="(profile, i) in profiles"
      :key="i"
      mb-4
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
          <v-card flat color="grey lighten-3" style="white-space:pre-line; word-wrap:break-word;">
            <v-card-text class="content" v-if="profile.contact">{{ profile.content }}</v-card-text>
            <v-card-text class="content" v-else-if="!profile.history" >{{ profile.content }}</v-card-text>
          </v-card>
          <!-- 4th -->
          <v-timeline dense v-if="profile.history">
            <v-timeline-item
              v-for="(time, i) in times"
              :key="i"
              :color="time.color"
              :small="time.small"
              :fill-dot="time.fill"
            >
              <div class="py-1">
                <a :href="time.link" :class="`${time.activeClass} ${time.color}--text text--darken-3`">{{ time.title }}</a>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-flex>
      </v-layout>
    </v-flex>
  </v-layout>
</template>
<script>
export default {
  data() {
    return {
      profiles: [
        {
          title: 'about',
          content: `熊本育ち．東京在住．
            現在バイタルデータ分析やスマートシティ検討の業務に携わりながら，プライベートで3DCADによるプロダクトデザインやデータ分析をしています．
            医療分野・エンターテインメント分野に貢献したいという思いがあります．`,
          contact: false,
          history: false,
        },
        {
          title: 'skill',
          content: `HTML, CSS, Vue, Nuxt, JQuery, Ruby, Rails, Python, XD, Fusion360`,
          contact: false,
          history: false,
        },
        {
          title: 'contact',
          content: `morinokumakamesan[at]gmail.com`,
          contact: true,
          history: false,
        },
        {
          title: 'history',
          content: "",
          contact: false,
          history: true,
        },
      ],
      times: [
        {
          color: 'teal',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2017',
        },
        {
          color: 'teal',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'SPAJAM 2017 出場',
          link: 'https://history.spajam.jp/2017/',
        },
        {
          color: 'teal',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ドコモハッカソン出場（優勝）',
        },
        {
          color: 'light-green',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2018',
        },
        {
          color: 'light-green',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'SPAJAM 2018 出場（優秀賞受賞）',
          link: 'https://history.spajam.jp/2018/',
        },
        {
          color: 'light-green',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'JPHACKS 2018 出場（ローカルスポンサー賞受賞）',
          link: 'https://jphacks.com/2018/',
        },
        {
          color: 'lime',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2019',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: '某社入社',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'XRジャム2019 出場（マイスターギルド賞，オニチク賞受賞）',
          link: 'https://osaka-driven-dev.connpass.com/event/127120/',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ラジオデザインコンテスト応募',
          link: 'http://localhost:3000/3dcads/1',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'KOKUYO DESIGN AWARD 2020 応募',
          link: 'http://localhost:3000/3dcads/2',
        },
        {
          color: 'amber',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2020',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'Youtube動画視聴回数予測コンペ 136位',
          link: 'https://comp.probspace.com/competitions/youtube-view-count',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ISUCON10参加',
          link: 'https://isucon.net/archives/54704557.html',
        },
        {
          color: 'orange',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2021',
        },
        {
          color: 'orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'Ubicomp 2021 Poster',
          link: 'https://dl.acm.org/doi/10.1145/3460418.3479308',
        },
        {
          color: 'orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'NoCodeBotリリース',
          link: 'https://prtimes.jp/main/html/rd/p/000000001.000086570.html',
        },
        {
          color: 'deep-orange',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2022',
        },
        {
          color: 'deep-orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'TOKYO MIDTOWN AWARD 2022応募',
          link: 'http://localhost:3000/3dcads/3',
        },
      ],
    }
  }
}
</script>
<style lang="scss">
.content {
  font-size: 18px;
}
.year {
  font-size: 20px;
}
.timeContent {
  font-size: 16px;
}
</style>
