<script >
import SearchVue from './Search.vue';
import { store } from '../store';
export default {
    name:'HeaderVue',
    components:{
      SearchVue
    },
    data(){
        return{
            store
        }
    }
}

</script>

<template>
    <header class="d-flex justify-content-between align-items-center p-2">
      <a class="p-2" href="#"><img src="../../public/netflix-clipart-file-3.png" alt="logo"></a>
      <SearchVue/>
    </header>
</template>

<style scoped lang="scss">
  header{
    height: 10vh;
    background: linear-gradient(rgb(0, 0, 0) 70%, rgb(63, 63, 63));
    border: 1px solid rgb(33, 33, 33);
    a{
      height: 90%;
      img{
        height: 100%;
      }
    }

  }
</style>