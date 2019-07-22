<template>
  <v-layout>
    <v-flex text-xs-center>
      <h1>{{ cad.title }}</h1>
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
export default {
  data(){
    return {
      id: this.$route.params.id,
      cads: [
        {
          id: '1',
          title: 'first'
        },
        {
          id: '2',
          title: 'second'
        }
      ]
    }
  },
  computed: {
    cad(){
      return this.cads.find(cad => cad.id === this.id)
    }
  }
}
</script>
