<template>
  <v-layout
    justify-center
    align-center
  >
    <v-flex
      text-xs-center
      md8
    >
      <Carousel :page-id="id" />
      <h2 style="margin: 3% 0 3%">* {{ cad.title }} *</h2>
      <p>{{ cad.content }}</p>
      <img
        src="/v.png"
        alt="Vuetify.js"
        class="mb-5"
      >
      <blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
        </footer>
      </blockquote>
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
          content: `「家に飾りたくなる手回し発電ラジオ」というコンセプトで，シンプルなデザインのラジオに仕上げました。ボタンをすべて本体フレームの内側に置くことにより，フルーエントなデザインを実現しています。どん家にも合うよう、白色フレームに黒色のつまみやボタンを採用しています。`
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
