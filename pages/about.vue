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
                <h2 :class="`${time.activeClass} ${time.color}--text text--darken-3`">{{ time.title }}</h2>
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
            現在IoTスマートホームの研究開発・商用化に携わりながら，趣味で3DCADによるプロダクトデザインやデータ分析をしています．
            医療・福祉分野に貢献したいという思いがあります．`,
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
          title: 'SPAJAM出場',
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
          title: 'SPAJAM出場（優秀賞受賞）',
        },
        {
          color: 'light-green',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'JPHACKS出場（ローカルスポンサー賞受賞）',
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
          title: 'XRジャム出場（マイスターギルド賞，オニチク賞受賞）',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ラジオデザインコンテスト応募',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'KOKUYO DESIGN AWARD 2019 応募',
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
