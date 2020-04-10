<template>
  <div class="progress">
    <p class="time">00:00</p>
    <progress max="100" value="30"></progress>
    <p class="total-time">03:40</p>
  </div>
</template>

<script lang="ts">
import { Vue } from 'vue-property-decorator'

export default class ProgressBar extends Vue {}
</script>

<style scoped>
.progress {
  width: 95%;
  display: grid;
  grid-template-columns: 1fr 5fr 1fr;
  grid-template-rows: 1fr;
  gap: 1rem;
}
p {
  font-weight: 300;
  font-size: 0.8rem;
}

.time {
  grid-column: 1/2;
  grid-row: 1/2;
  justify-self: end;
  align-self: center;
}

.total-time {
  grid-column: 3/4;
  grid-row: 1/2;
  align-self: center;
}

progress[value] {
  grid-column: 2/3;
  grid-row: 1/2;
  width: 100%;
  appearance: none;
  height: 4px;
  align-self: center;
  background-color: rgba(1, 22, 39, 0.2);
}

::-moz-progress-bar {
  background-color: #011627;
}
::-webkit-progress-value {
  background-color: #011627;
}
::-webkit-progress-inner-element {
  color: rgba(1, 22, 39, 0.2);
}
</style>