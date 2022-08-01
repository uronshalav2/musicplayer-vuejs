<template>
<div id="app">

    <main>
      <div class="container p-3 me-auto bg-black" id="app-container">
      <SongList/>        
      </div>
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
  color: white;
  background-color: black;
  overflow-x: hidden;
  height: 100vh;
}
#head{
  height: 60px;
  background-color: black;
  width: 400px;
  border-bottom: 0.8px solid #dc3545;
}
#head h2{
  line-height: 60px;
  font-weight: light;
}

#app-container{
  height: 842px;
  width: 400px;
}
@media only screen and (max-width: 667px){
  #app-container{
    width:350px;
  }
}

</style>
