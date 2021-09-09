<template>
    <nav class="text-center mb-3">
        <div v-for="(genre, index) in genreList" :key="index"  class="d-inline-block color_text mx-3">
            <input type="checkbox" :id="genre" :name="genre" :value="genre" v-model="checkedGenres">
            <label :for="genre" class="ms-2">{{genre}}</label>
        </div>
    </nav>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Nav',
    data () {
        return {
            genreList: [],
            checkedGenres: [],
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => { 
            res.data.response.forEach((song) => {
                if (!this.genreList.includes(song.genre)) {
                    this.genreList.push(song.genre);
                }
            })
        })
    }
}
</script>

<style lang="scss">
</style>