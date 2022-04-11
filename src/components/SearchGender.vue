<template>
    <div>
        <div class="text-center p-3">
            <select class="p-1" @change="$emit('search', mostraGenere($event))">
                <option value="All">All</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
  name: "SearchGender",
    methods:{
        mostraGenere(event){
            return event.target.value;
        },

    },
};
</script>

<style>
</style>