<template>
    <main class="d-flex flex-wrap justify-content-center p-3">
        <CardSong
            :key="index"
            v-for="(song,index) in songs"
            :Img="song.poster"
            :Title="song.title"
            :Author="song.author"
            :Year="song.year"
        />

    </main>
</template>

<script>

import CardSong from "@/components/CardSong.vue"
import axios from "axios"


export default {
    name: "MainComponent",

    components:{
        CardSong,
    },
    data() {
        return {
            songs:[],

        };
    },
    mounted(){
        this.generaCard();
    },
    methods: {
        generaCard() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((response)=>{
                this.songs=response.data.response
                console.log(this.songs)

            });
        },
    },


};
</script>


<style lang= 'scss' scoped>

main{
    background-color: #1e2d3b;
    width: 70%;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

}




</style>