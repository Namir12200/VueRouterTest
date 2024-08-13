<script setup>
    import { ref, onMounted } from 'vue';
    import { useRoute } from 'vue-router';

    const movie = ref({})
    const route = useRoute()

    onMounted(() => {
        fetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`).then((res) => res.json()).then((res) => {
            movie.value = res;
        });
    })

</script>

<template>
    <h3>{{ movie.title }}</h3>
    <p>{{ movie.body }}</p>
</template>