<template>
    <div>
        <ul>
            <li v-for="post in posts" :key="post['id']">
                {{ post.title }}
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: "App",
    components: {},

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