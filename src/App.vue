<template>
  <v-app>
    <p>{{ quizData[quizNow].quizText }}</p>
    <v-btn v-for="ans in ansList" :key="ans">{{ ans }}</v-btn>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      quizNow: 0,
      ansList: [],
      quizData: [
        {
          quizText: '「音威子府」なんて読む？',
          answerList: [ 'おといねっぷ', 'おんいしふ', 'おといこふ', 'おんいこふ' ],
        },
        {
          quizText: '「長万部」なんて読む？',
          answerList: [ 'おしゃまんべ', 'ちょうまんぶ', 'ながまんべ', 'おさまんぶ' ],
        },
        {
          quizText: '「神居古潭」なんて読む？',
          answerList: [ 'かむいこたん', 'かみいこたん', 'しんきょこたん', 'しんいこたん' ],
        },
        {
          quizText: '「占冠」なんて読む？',
          answerList: [ 'しむかっぷ', 'せんかん', 'しめかん', 'せんかんむり' ],
        },
        {
          quizText: '「忍路」なんて読む？',
          answerList: [ 'おしょろ', 'にんろ', 'しのびみち', 'にんみち' ],
        },
        {
          quizText: '「銭函」なんて読む？',
          answerList: [ 'ぜにばこ', 'ぜにだて', 'せんかん', 'ぜにかん' ],
        },
      ],
    }
  },
  computed: {},
  methods: {
    quizNumber() {
      this.quizNow =  Math.floor(Math.random() * 6)
    },
    ansShuffle() {
      this.ansList = this.quizData[this.quizNow].answerList.sort(()=> Math.random() - 0.5);
    }
  },
  mounted() {
    this.quizNumber()
    this.ansShuffle()
  }
}
</script>

<style scoped>

</style>