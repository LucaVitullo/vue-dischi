<template>
    <main class="pt-4 ">
        <SearchGender @search="filtraGenr"/>
        <div v-if="songs.length > 0" class="container d-flex flex-wrap justify-content-center gap-4 pt-2">
            <CardSong
                :key="index"
                v-for="(song,index) in mostraGenere"
                :Img="song.poster"
                :Title="song.title"
                :Author="song.author"
                :Year="song.year"
            />

        </div>
        <div v-else class="d-flex justify-content-center">
            <LoadingComponent/>
        </div>


    </main>
</template>

<script>

import CardSong from "@/components/CardSong.vue"
import axios from "axios"
import LoadingComponent from "@/components/LoadingComponent.vue"
import SearchGender from "@/components/SearchGender.vue"


export default {
    name: "MainComponent",

    components:{
        CardSong,
        LoadingComponent,
        SearchGender,
    },
    data() {
        return {
            songs:[],
            genereSelezionato:'',

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

        filtraGenr(genere){
            this.genereSelezionato = genere;
        },
    },

    computed:{
        mostraGenere(){
            if(this.genereSelezionato === "All") {
                return this.songs;
            }
            return this.songs.filter((element)=>{
                return element.genre.includes(this.genereSelezionato)
            })
        }
    }


};
</script>


<style lang= 'scss' scoped>

main{
    background-color: #1e2d3b;
    width: 70%;
    margin: auto;

}

.lv{
    width: 175px;
}



</style>