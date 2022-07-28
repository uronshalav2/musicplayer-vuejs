<template>
  <div id="songlist" class="contanier">
    <div  v-for="song in list" v-bind:key="song.id">
    <span class="text-danger">{{ song.name }}</span>
    <br />
    <span class="text-white">{{ song.artistName }} - <span class="text-secondary">{{song.albumName}} - {{song.year}}</span></span>
    </div>
    <div>
        <img v-bind:key="song.src">
    </div>
  </div>
</template>

<script>
export default {
    name:'SongList',
    data  () {
        return {
            list: [
            
                {
                    id: 1,
                    name: "Mockingbird",
                    artistName: "Eminem",
                    albumName:  "Encore",
                    year: 2004,
                    src:'https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/600x600bf-60.jpeg?alt=media&token=58eafd4c-0156-404f-a2f5-c9a03cac719a',
                    songSrc:'https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/Eminem_-_Mockingbird_Lyrics_(getmp3.pro)%20(1).mp3?alt=media&token=d57b6495-2d1c-4272-9752-8b33461317e1',
                },
                                {
                    id: 2,
                    name: "Like Toy Soldiers",
                    artistName: "Eminem",
                    albumName:  "Encore",
                    year: 2004,
                    src:'',
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
#imgs{
    width:250px;
    height: 250px;  
    background-size: cover;

}
</style>