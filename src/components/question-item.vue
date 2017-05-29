<template>
  <div >
    <div class="question">{{num+1}}、{{question.title}}</div>
    <div class="answer" v-for="(value, key, index) in question.answers">
      <label :for="'answer-'+num +'-'+ index">
        <input type="radio" :id="'answer-'+num +'-'+ index" :name="'question-'+num">{{key}}. {{value}}
      </label>

    </div>
  </div>
</template>

<script>
  export default{
    props:['question', 'num']
  }
</script>
