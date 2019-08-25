<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      text-xs-center
      md8
    >
      <h2 style="margin: 3% 0 2%">* {{ cad.title }} *</h2>
      <Carousel :page-id="id" />
      <p style="text-align:left;margin: 3% 0 3%">{{ cad.content }}</p>
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
          content: `「家に飾りたくなる手回し発電ラジオ」というコンセプトで，シンプルなデザインのラジオに仕上げました。ボタンをすべて本体フレームの内側に置くことにより，フルーエントなデザインを実現しています。どんな家にも合うよう、白色フレームに黒色のつまみやボタンを採用しています。`
        },
        {
          id: '2',
          title: 'second',
          content: ``
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
