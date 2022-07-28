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
  background: black;
  height: 70px;
  width: 100%;
  color:white;
}
header h3{
  line-height: 70px;
}

</style>
