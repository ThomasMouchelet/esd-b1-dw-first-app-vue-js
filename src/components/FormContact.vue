<script>
    import FilmsList from './FilmsList.vue';

    export default {
        name: 'FormContact',
        components: {
            FilmsList
        },
        data() {
            return {
                credentials: {
                    title: '',
                    duration: '',
                    notation: '',
                },
                filmsList: [],
            }
        },
        methods: {
            handleSubmit(){
                this.filmsList.push(this.credentials);
                this.credentials = {
                    title: '',
                    duration: '',
                    notation: '',
                    public: false,
                }
            },
            handleUpdatePublic(film){
                console.log('handleUpdatePublic', film);
                film.public = !film.public;
            }
        },
    }
</script>

<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" placeholder="Le titre du site" v-model="credentials.title">
        <input type="text" placeholder="Durée du film" v-model="credentials.duration">
        <input type="text" placeholder="Notation du film" v-model="credentials.notation">
        <div>
            <label for="public-on">Public On</label>
            <input id="public-on" type="radio" v-model="credentials.public" value="true">
            <label for="public-off">Public Off</label>
            <input id="public-off" type="radio" v-model="credentials.public" value="false">
        </div>
        <input type="submit" value="Envoyer">
    </form>

    <FilmsList :filmsList="filmsList" v-on:handleUpdatePublic="handleUpdatePublic" />
</template>