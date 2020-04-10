<template>
  <div class="footer-controls">
    <icon :name="mdiShuffle" @click.native="toggleShuffle" :color="shuffle ? '#011627' : '#a2aab0'"/>
    <div class="heart">
      <icon v-if="heart" :name="mdiHeart" @click.native="unHeart" color="#ff6b6b"/>
      <icon v-if="!heart" :name="mdiHeartOutline" @click.native="onHeart" color="#ff6b6b"/>
    </div>
    <div class="repeat">
      <icon v-if="repeat" :name="mdiRepeat" @click.native="repeatOff" color="#011627"/>
      <icon v-if="!repeat" :name="mdiRepeatOff" @click.native="repeatOn" color="#011627"/>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import Icon from './Icon.vue'
import { mdiRepeat, mdiRepeatOff, mdiHeart, mdiHeartOutline, mdiShuffle } from '@mdi/js'
@Component({
  data() {
    return {
      mdiRepeat,
      mdiRepeatOff,
      mdiHeart,
      mdiHeartOutline,
      mdiShuffle
    }
  },
  components: {
    Icon
  }
})
export default class FooterControls extends Vue {
  heart = false
  repeat = false
  shuffle = false
  toggleShuffle() {
    this.shuffle = !this.shuffle
  }
  onHeart() {
    this.heart = true
  }
  unHeart() {
    this.heart = false
  }
  repeatOff() {
    this.repeat = false
  }
  repeatOn() {
    this.repeat = true
  }
}
</script>

<style scoped>
.footer-controls {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
}
</style>