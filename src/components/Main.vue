<template>
    <main class="container mt-5 pt-5 mb-5">
        <Nav />
        <div class="row justify-content-center gx-4 gy-3">
            <article v-for="(album, index) in songList" :key="index" class="col-2">
                <Album :album='album'/>
            </article>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import Album from '../components/Album.vue';
import Nav from '../components/Nav.vue';

export default {
  name: 'Main',
  components: {
    Album,
    Nav,
  },
  data () {
    return {
    songList: {},
    selectedSongList: {},
    }
  },
  method: {

  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => { 
        this.songList = res.data.response;
    })
  }
}
</script>

<style lang="scss">
main {
    article {
        h4 {
            font-size: 20px;
        }
        time, address {
            font-size: 15px;
        }
    }
}
</style>