<script >
import Film from './Film.vue';
import Serie from './serie.vue';
import {store} from '../store';

export default {
    name:'MainVue',
    components:{
        Film,
        Serie
    },
    data(){
        return{
            store
        }
    },
}
</script>

<template>
    <div class="main">
        <Film v-for="(elem, index) in store.arrayFilmNome" :key="index" :propsFilmNome="elem"/>
        <Serie/>
    </div>
</template>

<style scoped lang="scss">
    .main{
        background-color: black;
        height: 90vh;
    }
</style>