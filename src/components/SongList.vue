<template>
  <div v-if="!isPlayerVisible">
    <div class="container mb-3" id="head">
      <h2 class="text-danger">Musical.</h2>
    </div>
    <div
      v-for="(song, songIndex) in list"
      v-bind:key="song.id"
      class="d-flex flex-row justify-content-between align-items-center text-start mb-4"
      id="songlist"
      v-on:click="playSong(songIndex)"
    >
      <div>
        <span class="text-danger">{{ song.name }}</span>
        <br />
        <span class="text-white"
          >{{ song.artistName }} -
          <span class="text-secondary"
            >{{ song.albumName }} - {{ song.year }}</span
          ></span
        >
      </div>
      <div>
        <img v-bind:src="song.src" class="img-fluid rounded" id="imgs" />
      </div>
    </div>
  </div>
  <div v-if="isPlayerVisible">
    <Player v-bind:song="list[currentSongIndex]" 
    @goback="isPlayerVisible = !isPlayerVisible"
    @next="playNext"
    @previous="playPrevious"/>
  </div>
</template>

<script>
import Player from "./Player.vue";
export default {
  name: "SongList",
  data() {
    return {
      isPlayerVisible: true,
      currentSongIndex: 0,
      list: [
        {
          id: 1,
          name: "Mockingbird",
          artistName: "Eminem",
          albumName: "Encore",
          year: 2004,
          src: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/600x600bf-60.jpeg?alt=media&token=58eafd4c-0156-404f-a2f5-c9a03cac719a",
          songSrc:
            "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/Eminem_-_Mockingbird_Lyrics_(getmp3.pro) (1).mp3?alt=media&token=d57b6495-2d1c-4272-9752-8b33461317e1",
        },
        {
          id: 2,
          name: "Like Toy Soldiers",
          artistName: "Eminem",
          albumName: "Encore",
          year: 2004,
          src: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/600x600.jpg?alt=media&token=1267ff67-03d8-473d-91b0-9dc7cfbdcb02",
          songSrc: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/Eminem%20-%20Like%20Toy%20Soldiers%20(Lyrics).mp3?alt=media&token=9c91944e-a728-47cb-8ed0-19b2dd4a479c",
        },
        {
          id: 3,
          name: "Hit 'Em Up",
          artistName: "2Pac",
          albumName: "Death Row Greatest Hits",
          year: 1996,
          src: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/2pac600.jpg?alt=media&token=628d3fb8-3681-4a2f-8aac-e3ee36537682",
          songSrc: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/2Pac%20-%20Hit%20'Em%20Up%20(Dirty)%20(Music%20Video)%20HD.mp3?alt=media&token=b22deea3-478e-4e51-a142-f63023f3b773",
        },
        {
          id: 4,
          name: "Praise The Lord",
          artistName: "A$AP Rocky",
          albumName: "Testing",
          year: 2018,
          src: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/testing.webp?alt=media&token=22579cfe-14eb-4d9f-9b75-f92700f9a772",
          songSrc: "https://firebasestorage.googleapis.com/v0/b/storage-project-2f0a7.appspot.com/o/A%24AP%20Rocky%20-%20Praise%20The%20Lord%20(Da%20Shine)%20(Lyrics).mp3?alt=media&token=e2303e49-f98a-4319-93b5-4ac48e38895b",
        },
      ],
    };
  },
  methods:{
    playSong(index){
      this.currentSongIndex = index;
      this.isPlayerVisible = true;
    },
      playNext(){
      if(this.currentSongIndex < this.list.length -1 ){
          this.currentSongIndex += 1;
      } else{
        this.currentSongIndex = 0;
      }

    },
      playPrevious(){
        if(this.currentSongIndex != 0){
          this.currentSongIndex -=1;
        } else{
          this.currentSongIndex = this.list.length - 1;
        }
      
    },

  },
  components: { Player },
};
</script>

<style scoped>
#imgs {
  width: 70px;
  height: 70px;
  background-size: cover;
}
#songlist{
  cursor:pointer;
}
</style>