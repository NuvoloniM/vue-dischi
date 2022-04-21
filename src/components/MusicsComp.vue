<template>
    <div>
        <div v-if="musicArray.length >= 10" class="row">
        <MusicCard 
        v-for="( element, index) in musicArray"
        :key="index"
        :poster="element.poster"
        :year="element.year"
        :title="element.title"
        :author="element.author"
        :genre="element.genre"
        />
        </div>
        <div v-else>
            <h2>LOADING</h2>
        </div>
    </div>
    
</template>

<script>

import MusicCard from './MusicCard.vue';
import axios from "axios";

export default {
    name: 'MusicsComp',
    components: {
        MusicCard,
    },
    data(){
        return {
            musicArray: [],
        }
    },
    created(){
        axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
            .then( (res) =>{
                this.musicArray = res.data.response;
            }
        )
    }
}
</script>
<style lang="scss" scoped>

    div {
        padding: 20px 0;
    }
    h2 {
        color: #fff;
        text-align: center;
    }
</style>