<template>

  <div id="app">   
    <MyHeader @searchKeyword="setParams"/>
    <MyMain :filmList="filmList" :seriesList="seriesList"/>
  </div>

</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  
  data(){
    return{
      apiUrl:'https://api.themoviedb.org/3',
      apiKey: '80278f7ae9fb5378d2944e6b0489885b',
      language: 'it-IT',
      filmList: [],
      seriesList:[]

    }
  },
  methods:{
  setParams(keyword){
    axios.get(this.apiUrl +'/search/movie?api_key='+ this.apiKey + '&language='+ this.language +'&query='+ keyword)
    .then(reply => {
      this.filmList= reply.data.results;
    })

    .catch(error =>{
    console.log (error);
    });
    
    axios.get(this.apiUrl +'/search/tv?api_key='+ this.apiKey + '&language='+ this.language +'&query='+ keyword)
    .then(reply => {
      this.seriesList= reply.data.results;
    })

    .catch(error =>{
    console.log (error);
    })



    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import '~@fortawesome/fontawesome-free/css/all.css';

</style>
