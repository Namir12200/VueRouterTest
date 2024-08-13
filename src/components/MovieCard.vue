<script setup>
    import { defineProps } from 'vue';

    // eslint-disable-next-line no-unused-vars
    const props = defineProps({
        movie: {
            required: true,
            type: Object
        }
    })

</script>

<template>
    <div>
        <RouterLink :to="`/movies/${movie.id}`">
            <h2>{{ movie.title }}</h2>
        </RouterLink>
        <br>
        <p>{{ movie.body }}</p>
    </div>
</template>