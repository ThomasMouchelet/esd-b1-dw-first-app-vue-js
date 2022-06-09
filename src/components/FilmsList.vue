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
            <!-- if public is false -->
            <!-- on click change value public -->
            <button v-on:click="() => this.$emit('handleUpdatePublic',film)">public</button>
            <!-- if public is true -->
            <!-- on click change value public -->
            <button>private</button>
        </li>
    </ul>
</template>