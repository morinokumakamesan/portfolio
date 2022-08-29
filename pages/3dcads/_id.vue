<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      text-xs-center
      md8
    >
      <p style="margin: 0% 0 0.5%; font-size: 1.2rem">コンペテーマ</p>
      <p style="font-size: 1.6rem">{{ cad.theme }}</p>
      <a :href="cad.url" style="margin: 0% 0 2%">{{ cad.link }}</a>
      <p style="margin: 3% 0 0%; font-size: 2rem; font-weight: bold;">* {{ cad.title }} *</p>
      <p style="text-align:left;margin: 2% 0 3%; white-space:pre-line; word-wrap:break-word; text-align: center;">{{ cad.content }}</p>
      <Carousel :page-id="id" />
    </v-flex>
  </v-layout>
</template>

<script>
import Carousel from '~/components/Carousel.vue'

export default {
  components: {
    Carousel
  },
  data(){
    return {
      id: this.$route.params.id,
      cads: [
        {
          id: '1',
          title: '手回し発電ラジオ',
          url: 'https://compe.japandesign.ne.jp/hisatomi-radiocompe-2019/',
          link: '久富電機産業株式会社ラジオデザインコンテスト2019',
          theme: '手回し発電機付きラジオのデザイン',
          content: `「家に飾りたくなる手回し発電ラジオ」というコンセプトで、シンプルなデザインのラジオに仕上げました。
          ボタンをすべて本体フレームの内側に置くことにより、フルーエントなデザインを実現しています。
          どんな家にも合うよう、白色フレームに黒色のつまみやボタンを採用しています。`
        },
        {
          id: '2',
          title: 'トンツーシャチハタ',
          url: 'https://compe.japandesign.ne.jp/news/2019/06/45019/',
          link: 'コクヨデザインアワード2020',
          theme: '♡',
          content: `あなたは人に想いを届けるとき、どのように伝えていますか？
          直接、電話、手紙、SNS.しかし想いは伝えたいけど、伝えるのは恥ずかしい。
          そしてどうしても周りにもばれたくない。
          そんなとき、手軽にトンツーで想いを表現できる文具を用意しました。

          決してずれのない想いを贈りたいあなたへ。`
        },
        {
          id: '3',
          title: 'Tangible Aroma',
          url: 'https://www.tokyo-midtown.com/jp/award/design/',
          link: 'TOKYO MIDTOWN AWARD 2022',
          theme: 'TRIP',
          content: `「香りに触れる」

          時に人を落ち着かせ、時に人の集中力を高め、そして、時に思い出を蘇らせる力も持っている香り。
          そんな香りを指先で感じることができれば、そこには新しい体験が待っているでしょう。
          香りとはとても複雑で、光の三原色にあたる「原臭」の定義は未だ曖昧です。
          そこで、Tangible Aromaでは、アロマの世界で定義される7種の香りに分類しました。
          いまの気分に合った香りを、あなたの指先の感覚で選んでみませんか。新しい香りの世界へ、あなたをいざないます。`
        }
      ],
    }
  },
  computed: {
    cad(){
      return this.cads.find(cad => cad.id === this.id)
    }
  }
}
</script>
