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


<style lang= 'scss'>

header{
    background-color: black;
}
header img{
    width: 50px;
}

</style>