<script>
    export default {
        name: 'FilmsList',
        props:["filmsList"],
    }
</script>

<template>
    <ul>
        <li v-for="film in filmsList" v-bind:key="film.title">
            {{ film.title }}
            
        </li>
    </ul>
</template>