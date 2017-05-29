<template>
  <div id="app">
    <div id="quiz">
      <question-item
        v-for="(currentQuestion, questionNumber) in questions"
        :key="questionNumber"
        :question="currentQuestion"
        :num="questionNumber"
        ></question-item>
    </div>
    <div id="submit">
      <button type="button">提交答案</button>
    </div>
    <div id="results"></div>
  </div>
</template>

<script>
  import questions from './questions'
  import questionItem from './components/question-item.vue'
  export default {
    name: 'app',
    components: {
      questionItem
    },
    data() {
      return {
        questions
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
