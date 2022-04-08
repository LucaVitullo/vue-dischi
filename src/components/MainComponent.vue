<template>
    <main class="pt-5">
        <div v-if="songs.length > 0" class="container d-flex flex-wrap justify-content-center gap-4">
            <CardSong
                :key="index"
                v-for="(song,index) in songs"
                :Img="song.poster"
                :Title="song.title"
                :Author="song.author"
                :Year="song.year"
            />

        </div>
        <div v-else>
            <LoadingComponent/>
        </div>


    </main>
</template>

<script>

import CardSong from "@/components/CardSong.vue"
import axios from "axios"
import LoadingComponent from "@/components/LoadingComponent.vue"


export default {
    name: "MainComponent",

    components:{
        CardSong,
        LoadingComponent,
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
                //console.log(this.songs)

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

}




</style>