<template>
    <div class="blogs">
        <h2>Blogs</h2>
        <div v-for="post in posts"
             :key="post.id">
            <span>{{ blog.title }}</span>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Blogs',
    data() {
        return {
            posts: []
        };
    },
    methods: {

    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts/')
            .then(response => {
                this.posts = response.data;
            });
    }
}
</script>

<style scoped>

</style>


