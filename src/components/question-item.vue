<template>
  <div >
    <div class="question">{{num+1}}、{{question.title}}</div>
    <div class="answer"
         v-for="(value, key, index) in question.answers"
         :class = "{right:show&&question.select=== question.correctAnswer, error:show&&question.select!== question.correctAnswer}"
      >
      <label
        :for="'answer-'+num +'-'+ index"
        >
        <input type="radio"
               :id="'answer-'+num +'-'+ index"
               :value="key"
               :name="'question-'+num"
               v-model="question.select"
        >{{key}}. {{value}}
      </label>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default{
    props: {
      question: {
        type: Object
      },
      num: {
        type: Number
      },
      show: {
        type: Boolean,
        default: false
      }
    },
    created () {
      Vue.set(this.question, 'select', '')
    }
  }
</script>

<style scoped>
  .question{
    font-size: 30px;
    margin-bottom: 10px;
  }
  .answers {
    margin-bottom: 20px;
    text-align: left;
    display: inline-block;
  }
  .answers label{
    display: block;
    margin-bottom: 10px;
  }
  .answer.right{
    color: lightgreen;
  }
  .answer.error{
    color: red;
  }
</style>
