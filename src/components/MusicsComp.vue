<template>
    <div>
        <div v-if="musicArray.length >= 10" class="row">
        <MusicCard 
        v-for="( element, index) in filterMusic()"
        :key="index"
        :poster="element.poster"
        :year="element.year"
        :title="element.title"
        :author="element.author"
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
    data() {
        return {
            musicArray: [],
        }
    },
    props: {
        valore: String,
    },
    created(){
        axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
            .then( (res) =>{
                this.musicArray = res.data.response;
            }
        )
    },
    methods: {
        filterMusic(){
            if( this.valore == ""){
                return this.musicArray;    
            } else {
                return this.musicArray.filter( (elem) => {
                    return elem.genre.toLowerCase().includes(this.valore.toLowerCase());
                } )
            }
        }
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