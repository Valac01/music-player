<template>
  <div class="controls">
    <icon :name="mdiSkipPrevious" />
    <button @click="playPause">
      <icon v-if="paused" :name="mdiPlay" color="#ffffff" size="3rem"/>
      <icon v-if="!paused" :name="mdiPause" color="#ffffff" size="3rem"/>
    </button>
    <icon :name="mdiSkipNext" />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import Icon from './Icon.vue'
import { mdiPlay, mdiPause, mdiSkipNext, mdiSkipPrevious } from '@mdi/js'

@Component({
  data() {
    return {
      mdiPlay,
      mdiPause,
      mdiSkipNext,
      mdiSkipPrevious
    }
  },
  components: {
    Icon
  }
})
export default class Controls extends Vue {
  paused = false

  playPause() {
    if(this.paused) {
      this.play()
      return
    }
    if(!this.paused) {
      this.pause()
      return
    }
  }
  play() {
    this.paused = false
  }

  pause() {
    this.paused = true
  }
}
</script>

<style scoped>
.controls {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 80%;
}
button {
  appearance: none;
  background-color: #011627;
  border-radius: 50%;
  border-width: 0;
  padding: 0.8rem;
  cursor: pointer;
  box-shadow: 0px 0px 4rem rgba(1, 22, 39, 0.8);
  transition: 10ms linear;
}

button:active {
  transform: scale(0.9);
  box-shadow: 0px 0px 4rem rgba(1, 22, 39, 1);
}
</style>