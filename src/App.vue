<template>
  <div id="app">
    <div id="quiz">
      <div v-for="(currentQuestion, questionNumber) in questions">
        <div class="question">{{questionNumber+1}}、{{currentQuestion.question}}</div>
        <div class="answer" v-for="(value, key) in currentQuestion.answers">
          <label for="'question-'+questionNumber"><input type="radio" :name="'question-'+questionNumber"></label>
          {{key}}. {{value}}
        </div>
      </div>

    </div>
    <div id="submit"></div>
    <div id="results"></div>
  </div>
</template>

<script>
  import questions from './questions'
  export default {
    name: 'app',
    components: {},
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
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
