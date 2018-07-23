<template>
    <div class="blogs">
        <h2>Blogs</h2>
        <div v-for="(blog, index) in blogData"
             :key="index">
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
            blogData: []
        };
    },
    methods: {

    },
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts/')
            .then(response => {
                this.blogData = response.data;
                console.log(response.data);
            })
    }
}
</script>

<style scoped>

</style>


