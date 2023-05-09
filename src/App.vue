<script >
import HeaderVue from './components/Header.vue';
import Film from './components/Film.vue';
import Serie from './components/serie.vue';
import axios from 'axios';
import { store } from './store';

export default{
  name:'app',
  components:{
    HeaderVue,
    Film,
    Serie
  },
  data(){
        return{
            store
        }
    }
}
</script>

<template>
  <div class="webApp">
    <HeaderVue/>
  </div>
</template>

<style lang="scss">
@use './style/main.scss';

  .webApp{
    height: 100vh;
  }

</style>
