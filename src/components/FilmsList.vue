<script>
    export default {
        name: 'FilmsList',
        props:["filmsList"],
    }
</script>

<style scoped>
    li.off{
        background: red;
        color: #fff;
    }
</style>

<template>
    <ul>
        <li :class="{off: !film.public}" v-for="film in filmsList" :key="film.title">
            {{ film.title }}
            
            <button v-on:click="() => this.$emit('handleUpdatePublic',film)">
                {{ film.public ? 'Private' : 'Public' }}
            </button>
            
        </li>
    </ul>
</template>