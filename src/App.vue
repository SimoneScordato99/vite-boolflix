<script >
import HeaderVue from './components/Header.vue';
import axios from 'axios';
import { store } from './store';
import MainVue from './components/MainVue.vue';

export default{
  name:'app',
  components:{
    HeaderVue,
    MainVue
},
  data(){
      return{
          store
      }
  },
  created(){
    this.callApiRicercaFilm()   
  },
  methods:{
      callApiRicercaFilm(){
        if(store.ricercato==''){
          axios.get(`https://api.themoviedb.org/3/trending/movie/week?api_key=53d1d2a5ec9c48ff0724060e43b0d094`)
          .then((res)=>{
              const film = res.data.results
              store.arrayFilmNome = film
          }),
          axios.get(`https://api.themoviedb.org/3/trending/tv/week?api_key=53d1d2a5ec9c48ff0724060e43b0d094`)
          .then((ress)=>{
              const serie = ress.data.results
              store.arraySerieNome = serie
          })
        } else {
          axios.get(`https://api.themoviedb.org/3/search/movie?api_key=53d1d2a5ec9c48ff0724060e43b0d094&query=${store.ricercato}`)
          .then((res)=>{
              const film = res.data.results
              store.arrayFilmNome = film
          }),
          axios.get(`https://api.themoviedb.org/3/search/tv?api_key=53d1d2a5ec9c48ff0724060e43b0d094&query=${store.ricercato}`)
          .then((ress)=>{
              const serie = ress.data.results
              store.arraySerieNome = serie
          })
        }
      }
      
  }
}
</script>

<template>
  <div class="webApp">
    <HeaderVue @emitRicerca="callApiRicercaFilm"/>
    <MainVue/>
  </div>
</template>

<style lang="scss">
@use './style/main.scss';

  .webApp{
    height: 100%;
    background-color: black;
  }

</style>
