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
        <div class="films">
            <Film v-for="(elem, index) in store.arrayFilmNome" :key="index" :propsFilmNome="elem"/>
        </div>
        <div class="films">
            <Serie v-for="(elem, index) in store.arraySerieNome" :key="index" :propsSerieNome="elem"/>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .main{
        background-color: black;
        padding-bottom: 40px;
        
        .films{
            display: flex;
            justify-content: space-between;
            overflow-x: scroll;
            padding-bottom: 10px;
            margin-bottom: 20px;
            
                        
        }
        

    }
</style>