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
          axios.get(`https://api.themoviedb.org/3/search/movie?api_key=53d1d2a5ec9c48ff0724060e43b0d094&query=${store.ricercato}`)
          .then((res)=>{
              const mario = res.data.results
              store.arrayFilmNome = mario
          })
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
    height: 100vh;
  }

</style>
