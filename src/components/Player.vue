<template>
<audio v-bind:src="song.songSrc" preload="auto" autoplay ref="audioPlayer"/>
  <div id="player">
    <div
      class="
        d-flex
        flex-row
        justify-content-between
        align-items-center
        mt-3
        mb-4
      "
    >
      <Button v-on:click="goback" class="btn btn-danger" id="backbutton">Back</Button>
      <div class="text-danger" id="titletwo">Musical</div>
    </div>
    <div>
      <img class="img-fluid" v-bind:src="song.src" />
      <div class="text-start">
        <p class="text-danger" id="songName">{{song.name}}</p>
        <p class="text-secondary" id="songArtist">{{song.artistName}} - {{song.albumName}}</p>
        <p class="text-secondary">{{song.year}}</p>
      </div>
    </div>
    <div class="row mt-5">
      <div class="col d-flex align-items-center justify-content-center">
        <button v-on:click="previous" class="btn btn-outline-danger" id="previousbutton">Previous</button>
      </div>
      <div class="col d-flex align-items-center justify-content-center">
        <button v-on:click="togglePlay" class="btn btn-outline-danger" id="playbutton">{{isPlaying ? 'Pause' : 'Play'}}</button>
      </div>
      <div class="col d-flex align-items-center justify-content-center">
        <button v-on:click="next" class="btn btn-outline-danger" id="nextbutton">Next</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return{
      isPlaying:true
    }
  },
  name: "Player",
  props: {
    song: {
      id: Number,
      name: String,
      artistName: String,
      albumName: String,
      year: Number,
      src: String,
      songSrc: String,
    },
  },
  emits:['goback','next','previous'],
  methods:{
    goback(){
      this.$emit('goback');
    },
    togglePlay(){
      if(this.isPlaying){
        this.$refs.audioPlayer.pause();
      } else{
        this.$refs.audioPlayer.play();
      }
      this.isPlaying = !this.isPlaying;
    },
    next(){
      this.$emit('next');
    },
    previous(){
      this.$emit('previous')
    },
  }
};
</script>

<style scoped>
#titletwo {
  font-size: 24px;
  font-weight: bolder;
}
#backbutton {
  font-weight: bolder;
  border: none;
  outline: none;
}
#backbutton:hover {
  background: white;
  color: #dc3545;
  border: none;
  outline: none;
}

#songName{
  font-weight: bolder;
  font-size: 25px;
  margin-bottom: 0;
}
#songArtist{
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 0;
}
#playbutton{
  width: 100px;
  height: 100px;
  border-radius: 50%;
  font-weight: bold;
}
#nextbutton{
  font-weight:bolder;
}
#previousbutton{
  font-weight: bolder;
}
</style>