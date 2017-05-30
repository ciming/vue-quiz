<template>
  <div id="app">
    <div id="quiz" class="quiz-container">
      <question-item
        class="slide"
        :class="{active: currentSlide===questionNumber}"
        v-for="(currentQuestion, questionNumber) in questions"
        :key="questionNumber"
        :question="currentQuestion"
        :num="questionNumber"
        :show="showResult"
      ></question-item>
    </div>
    <div id="submit">
      <button id="previous" v-if="currentSlide>0" @click="currentSlide--">上一题</button>
      <button id="next" v-if="currentSlide<questions.length-1" @click="currentSlide++">下一题</button>
      <button type="button" @click="submit">提交答案</button>
    </div>
    <div id="results" v-if="showResult">
      共{{questions.length}}题，{{numCorrect}}题正确
    </div>
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
      /**
       * @property {Object} questions 问题数组
       * @property {Number} currentSlide 当前问题索引
       * @property {Boolean} showResult 是否显示答案
       * @property {Number} numCorrect 答题错误个数
       */
      return {
        questions,
        currentSlide: 0,
        showResult: false,
        numCorrect: 0
      }
    },
    created() {
    },
    methods: {
      /**
       * 检查错误个数
       */
      check() {
        let numCorrect = 0;
        this.questions.forEach((question, num) => {
          if (question.select === question.correctAnswer) {
            numCorrect++
          }
        })
        this.numCorrect = numCorrect
      },
      submit() {
        this.check();
        this.showResult = true;
      }
    }
  }
</script>

<style>
  body{
    background-color: #f8f6f0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }

  .slide{
    position: absolute;
    left: 0px;
    top: 0px;
    width: 100%;
    z-index: 1;
    opacity: 0;
    transition: opacity 0.5s;
  }
  .slide.active{
    opacity: 1;
    z-index: 2;
  }
  .quiz-container{
    position: relative;
    height: 200px;
    margin-top: 40px;
  }
  button{
    font-family: 'Work Sans', sans-serif;
    font-size: 16px;
    background-color: #279;
    color: #fff;
    border: 0px;
    border-radius: 3px;
    padding: 10px;
    cursor: pointer;
    margin-bottom: 20px;
  }
  button:hover{
    background-color: #38a;
  }
</style>
