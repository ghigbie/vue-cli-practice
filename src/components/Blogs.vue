<template>
    <div class="blogs">
        <h2>Blogs</h2>
        <input type="text" v-model="searchTerm"/>
        <div v-for="post in posts"
             :key="post.id">
            <h3>{{ post.title }}</h3>
            <p>{{ post.body | snippet }}</p>
        </div>
        <div v-if="err">
            {{ errMessage }}
        </div>  
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Blogs',
    data() {
        return {
            posts: [],
            err: '',
            errMessage: 'There was an error. Please try again',
            searchTerm: ''
        };
    },
    methods: {

    },
    computed: {
        filteredPosts() {
           return  this.posts.filter(post => {
               post.body === this.searchTerm;
           })
        }
    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts/')
            .then(response => {
                this.posts = response.data;
            }).catch(err => {
                console.log(err);
                this.err = err;
            });
    }
}
</script>

<style scoped>

</style>


