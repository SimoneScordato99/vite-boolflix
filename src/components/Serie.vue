<script >
import {store} from '../store'
export default {
    name:'Serie',
    props:['propsSerieNome'],
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
        console.log()
        let tiziano = this.propsSerieNome.original_language
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
    <img :src=" `https://image.tmdb.org/t/p/w342${propsSerieNome.poster_path}` " alt="">
    <div class="card-body position-absolute p-0">
      <h5 class="card-title fs-4">{{ propsSerieNome.name }}</h5>
      <div class="scroll position-absolute">
        <p class="card-text  fs-6 p-0">{{ propsSerieNome.overview }}</p>
      </div>
      <img :src=" `https://flagsapi.com/${up()}/flat/64.png`" alt="bandiera" class="card-flag position-absolute">
      <div class="card-stelle d-flex position-absolute">
        <i class="fa-solid fa-star coloreStella" v-for="(elem, index) in Math.round(this.propsSerieNome.vote_average / 2)"></i>
        <i class="fa-solid fa-star" v-for="(elem, index) in 5 - Math.round(this.propsSerieNome.vote_average / 2)"></i>
      </div>
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
        .scroll{
          overflow-y: scroll;
          height: 210px;
        }
        .coloreStella{
          color: goldenrod;
        }
      }
      img{
        width: 30px;
        display: none;
      }
      .card-text{
        text-align: center;
        bottom: 60px;
        left: 10px;
      }
      .scroll{
        overflow-y: hidden;
        height: 210px;
        
      }
      .card-title{
        text-align: center;
        padding-top: 5px;
        height: 60px;
        overflow-y: hidden;
      }
      .card-flag{
        bottom: 10px;
        left: 10px;
      }
      .card-stelle{
        bottom: 50px;
        left: 10px;
      }
      
    }
    
  }
</style>