<template>
  <div class="album">
    <img :src="require(`@/assets/songs/${art}.png`)" alt="Album Art" class="album__art">
    <img aria-hidden :src="require(`@/assets/songs/${art}.png`)" alt="Album Art" class="album__shadow">
  </div>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
export default class AlbumArt extends Vue {
  @Prop() readonly art!: string
}
</script>

<style scoped>
.album {
  --album-height: 300px;
  --album-width: 280px;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: max-content;
  margin: 0 1.5rem;
}
.album__art {
  height: var(--album-height);
  width: var(--album-width);
  object-fit: cover;
  object-position: center center;
  border-radius: 1rem;
  grid-row: 1/2;
  grid-column: 1/2;
  z-index: 2;
}
.album__shadow {
  height: var(--album-height);
  width: var(--album-width);
  object-fit: cover;
  object-position: center center;
  grid-row: 1/2;
  grid-column: 1/2;
  z-index: 1;
  margin-top: 25px;
  filter: blur(40px) saturate(8) opacity(0.5);
}
</style>