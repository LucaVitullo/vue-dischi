<template>
    <header>
        <img :src="logo" :alt="logo">
    </header>
</template>

<script>
import logo from "@/assets/spotify-logo.png";



export default {
    name: "HeaderComponent",
    data(){
        return{
            logo: logo,
        }
    }

}
</script>


<style lang= 'scss' scoped>

header{
    background-color: black;
}

</style>