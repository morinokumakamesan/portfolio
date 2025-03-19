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
          title: 'About',
          content: `本業ではAI✕ヘルスケア関連の研究開発に従事。
            その傍らプライベートでWebアプリ開発の業務委託を受けたり、趣味でプロダクトデザインやサッカーのデータ分析をしています。
            主にHCI（Human Computer Interaction）分野に野に興味があります。`,
          contact: false,
          history: false,
        },
        {
          title: 'Skill',
          content: `HTML, CSS, Vue, Nuxt.js, Node.js, jQuery, Ruby, Rails, Python, Flask, XD, Fusion360, Ardupilot`,
          contact: false,
          history: false,
        },
        {
          title: 'Contact',
          content: `morinokumakamesan[at]gmail.com`,
          contact: true,
          history: false,
        },
        {
          title: 'History',
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
          title: '2024',
        },
        {
          color: 'teal',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: '17th SHACHIHATA NEW Product Design Award',
          link: 'https://morinokumakamesan.netlify.app/3dcads/4',
        },
        {
          color: 'green',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2023',
        },
        {
          color: 'green',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'UbiComp2023 Poster',
          link: 'https://dl.acm.org/doi/10.1145/3594739.3610690',
        },
        {
          color: 'light-green',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2022',
        },
        {
          color: 'light-green',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'TOKYO MIDTOWN AWARD 2022応募',
          link: 'https://morinokumakamesan.netlify.app/3dcads/3',
        },
        {
          color: 'lime',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2021',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'Ubicomp2021 Poster',
          link: 'https://dl.acm.org/doi/10.1145/3460418.3479308',
        },
        {
          color: 'lime',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'NoCodeBotリリース',
          link: 'https://prtimes.jp/main/html/rd/p/000000001.000086570.html',
        },
        {
          color: 'yellow',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2020',
        },
        {
          color: 'yellow',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'Youtube動画視聴回数予測コンペ 136位',
          link: 'https://comp.probspace.com/competitions/youtube-view-count',
        },
        {
          color: 'yellow',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ISUCON10参加',
          link: 'https://isucon.net/archives/54704557.html',
        },
        {
          color: 'amber',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2019',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: '某社入社',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'XRジャム2019 出場（マイスターギルド賞，オニチク賞受賞）',
          link: 'https://osaka-driven-dev.connpass.com/event/127120/',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ラジオデザインコンテスト応募',
          link: 'https://morinokumakamesan.netlify.app/3dcads/1',
        },
        {
          color: 'amber',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'KOKUYO DESIGN AWARD 2020 応募',
          link: 'https://morinokumakamesan.netlify.app/3dcads/2',
        },
        {
          color: 'orange',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2018',
        },
        {
          color: 'orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'SPAJAM 2018 出場（優秀賞受賞）',
          link: 'https://history.spajam.jp/2018/',
        },
        {
          color: 'orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'JPHACKS 2018 出場（ローカルスポンサー賞受賞）',
          link: 'https://jphacks.com/2018/',
        },
        {
          color: 'deep-orange',
          small: false,
          fill: false,
          activeClass: 'year',
          title: '2017',
        },
        {
          color: 'deep-orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: '電気・情報関係学会九州支部連合大会講演奨励賞',
          link: 'https://www.ieice.org/jpn/about/j_pdf/2018/2017jh.pdf',
        },
        {
          color: 'deep-orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'SPAJAM 2017 出場',
          link: 'https://history.spajam.jp/2017/',
        },
        {
          color: 'deep-orange',
          small: true,
          fill: true,
          activeClass: 'timeContent font-weight-light',
          title: 'ドコモハッカソン出場（優勝）',
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
