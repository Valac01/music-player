<template>
  <div id="app">
    <div class="album-wrapper center-column">
      <album-art art="cover" />
    </div>
    <name class="name-wrapper center-column"/>
    <progress-bar class="progress-wrapper center-column"/>
    <controls class="controls-wrapper center-column"/>
    <footer-controls class="footer-controls-wrapper center-column"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import AlbumArt from './components/AlbumArt.vue';
import Name from './components/Name.vue';
import ProgressBar from './components/ProgressBar.vue';
import Controls from './components/Controls.vue';
import FooterControls from './components/FooterControls.vue';


@Component({
  components: {
    Controls,
    Name,
    FooterControls,
    AlbumArt,
    ProgressBar
  },
})
export default class App extends Vue {}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Montserrat', sans-serif;
}

#app {
  height: 100vh;
  width: 100vw;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 8fr 2fr 1fr 2fr 1fr;
  overflow: hidden;
}

.center-column {
  grid-column: 1/2;
  justify-self: center;
  align-self: center;
}

.album-wrapper {
  grid-row: 1/2;
  display: flex;
}

.name-wrapper {
  grid-row: 2/3;
}

.progress-wrapper {
  grid-row: 3/4;
}

.controls-wrapper {
  grid-row: 4/5;
} 

.footer-controls-wrapper {
  grid-row: 5/6;
}
</style>
