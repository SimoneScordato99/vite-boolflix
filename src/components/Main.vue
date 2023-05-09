<script >
import Film from './Film.vue';
import Serie from './serie.vue';
import {store} from '../store';
export default {
    name:'Main',
    components:{
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
    <div class="main">
        <Film/>
        <Serie/>
    </div>
</template>

<style scoped lang="scss">
    .main{
        background-color: black;
    }
</style>