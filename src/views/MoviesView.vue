<script setup>
    import { ref, onMounted } from 'vue';
    import MovieCard from '../components/MovieCard.vue'
    const movieList = ref([]);

    onMounted(() => {
        fetch("https://jsonplaceholder.typicode.com/posts").then((response) => response.json()).then((res) => {
            movieList.value = res;
        })
    })

</script>

<template>
    <h1>Movies List</h1>
    <ul>
        <li v-for="movie in movieList" :key="movie.id">
            <MovieCard :movie="movie" />
        </li>
    </ul>
</template>