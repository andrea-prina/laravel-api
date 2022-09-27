<template>
    <div>
        <Main :posts="posts"/>
    </div>
</template>

<script>
import Main from '../components/Main.vue';
import axios from 'axios';

export default {
    name: "App",
    components: {
        Main,
    },

    data : function(){
        
        return {
            posts : [],
        }
    },

    methods : {

        getPosts : function(){

            axios.get(`http://127.0.0.1:8000/api/posts`)
            .then((result) => {
                this.posts = result.data.results.data;
            })
            .catch((err) => {
                console.warn(err);
            })
        }
    },

    created(){
        this.getPosts();
    }

}
</script>

<style>

</style>