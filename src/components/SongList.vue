<template>
  <div id="songlist" class="contanier">
    <div  v-for="song in list" v-bind:key="song.id">
    <span class="text-warning">{{ song.name }}</span>
    <br />
    <span class="text-secondary">{{ song.artistName }} - {{song.albumName}} - {{song.year}}</span>

    </div>
  </div>
</template>

<script>
export default {
    data () {
        return {
            list: [
                
                {
                    id: 1,
                    name: "Mockingbird",
                    artistName: "Eminem",
                    albumName:  "Encore",
                    year: 2004,
                    src:"https://m.media-amazon.com/images/M/MV5BNTJiN2M1N2YtOGM1NC00YzVmLTkxYTctMGI3NzNiY2Q1ODcyXkEyXkFqcGdeQXVyNzU3Nzk4MDQ@._V1_.jpg",
                    songSrc:"gs://storage-project-2f0a7.appspot.com/Eminem_-_Mockingbird_Lyrics_(getmp3.pro) (1).mp3",
                },
                                {
                    id: 2,
                    name: "Like Toy Soldiers",
                    artistName: "Eminem",
                    albumName:  "Encore",
                    year: 2004,
                    src:"https://m.media-amazon.com/images/M/MV5BNTJiN2M1N2YtOGM1NC00YzVmLTkxYTctMGI3NzNiY2Q1ODcyXkEyXkFqcGdeQXVyNzU3Nzk4MDQ@._V1_.jpg",
                    songSrc:"",
                },
            ]
        }
    }
}
</script>

<style scoped>

#songlist{
    background: black;

}
</style>