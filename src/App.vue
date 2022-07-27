<template>
<div id="app">
    <header>
      <h3>Musical</h3>
    </header>
    <main>
      <SongList/>
    </main>
  </div>
</template>

<script>
import SongList from './components/SongList.vue';

export default {
  name: 'App',
  components: {
    SongList
}
}
</script>

<style>
#app {
  font-family: 'Raleway', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}
header{
  background: #4981ac;
  height: 80px;
  width: 100%;
  color:white;
}
header h3{
  line-height: 80px;
}
.player{
  position: relative;
  width: 350px;
  background-color: #f1f3f4;
  box-shadow:0 50px 80px rgba(0,0,0,0.25);
}
.player .imgBx{
    position: relative;
    width: 100%;
    height: 350px;
}
.player  .imgBx img{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.sounds{
  text-align: center;
  font-weight: bolder;
  font-size: 26px;
}
</style>
