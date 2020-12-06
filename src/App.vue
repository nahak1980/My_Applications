<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <directives></directives> -->
    <!-- <bind-directive></bind-directive> -->
    <!-- <use-function></use-function> -->

    <Header />

    <b-container class="bv-example-row">
    <b-row>
      <b-col sm="6" offset="3"><QuestionBox 
        v-if="data.questions.length"
       :currentQuestion="data.questions[data.index]"
       :next="next"
      /></b-col>
    </b-row>
    </b-container>
    
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import Directives from './components/Directives.vue'
//import BindDirective from './components/BindDerictive.vue'
// import UseFunction from './components/UseFunction.vue'

import Header from './components/Header.vue';
import QuestionBox from './components/QuestionBox.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    //Directives
    //HelloWorld
    //BindDirective
    // UseFunction
    Header,
    QuestionBox
  },

  mounted() {
    axios.get(`https://opentdb.com/api.php?amount=10&category=27&type=multiple`)
    .then((result)=>{
      this.data.questions = result.data.results;
      console.log(this.data.questions);
    })
  },

  data() {
    return {
      data: {
        questions: [],
        index: 0
      }
    }
  },

  methods: {
    next(){
      this.data.index++;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
