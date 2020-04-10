<template>
  <div>
    <h2>Alone Together</h2>
    <h4><span>Fall Out Boy</span> &bull; <span>Save Rock and Roll</span></h4>
  </div>
</template>

<script lang="ts">
import {Vue, Component} from 'vue-property-decorator'

@Component
export default class Name extends Vue {}
</script>

<style scoped>
div {
  text-align: center;
  color: #011424;
}
h2 {
  font-weight: 700;
  font-size: 1.8rem;
  margin-bottom: 0.8rem;
  text-transform: uppercase;
}
h4 {
  font-weight: 300;
}
</style>