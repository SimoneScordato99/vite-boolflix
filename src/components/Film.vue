<script >
import {store} from '../store'
export default {
    name:'Film',
    props:['propsFilmNome'],
    data(){
      return{
        store
      }
    },
    created(){
      this.up()
    },  
    methods:{
      up(){
        
        let tiziano = this.propsFilmNome.original_language
        if(tiziano=='en'){
          tiziano='gb'
        }
        else if(tiziano=='ja'){
          tiziano='jp'
        }
        else if(tiziano=='zh'){
          tiziano='cn'
        }
        else if(tiziano=='ko'){
          tiziano='kr'
        }
        let fabrizio = tiziano.toUpperCase()
        return fabrizio
      }
    }
}
</script>

<template>
    <div class="card"> 
      <img :src=" `https://image.tmdb.org/t/p/w342${propsFilmNome.poster_path}` " alt="">
      <div class="card-body position-absolute p-0">
        <h5 class="card-title fs-4">{{ propsFilmNome.title }}</h5>
        <p class="card-text fs-6 p-0">{{ propsFilmNome.overview }}</p>
        <img :src=" `https://flagsapi.com/${up()}/flat/64.png`" alt="bandiera" class="card-flag position-absolute">
        <p class="card-text card-vote fs-6 p-0 position-absolute">{{ propsFilmNome.vote_average }}</p> 
      </div>
    </div>
</template>

<style scoped lang="scss">
    .card{
    
    margin: 30px 30px;
    min-width: 250px;
    background-color: black;
    color: white;
    box-shadow: 0 0 30px rgb(36, 36, 36);
    img{
      width: 100%;
    }
    .card-body{
      color: rgba(0, 0, 0, 0);
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      &:hover{
        background-color: rgba(0, 0, 0, 0.6);
        color: rgb(255, 255, 255);
        img{
          display: block;
        }
      }
      img{
        width: 30px;
        display: none;
      }
      .card-text{
        text-align: center;
      }
      .card-title{
        text-align: center;
        padding-top: 15px;
      }
      .card-flag{
        bottom: 35px;
        left: 10px;
      }
      .card-vote{
        bottom: 10px;
        left: 10px;
      }
    }
    
  }
</style>