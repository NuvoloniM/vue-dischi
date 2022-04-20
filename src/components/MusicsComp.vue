<template>
    <div class="row">
        <MusicCard 
        v-for="( element, index) in musicArray"
        :key="index"
        :poster="element.poster"
        :year="element.year"
        :title="element.title"
        :author="element.author"
        />
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

</style>