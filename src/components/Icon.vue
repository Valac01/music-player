<template>
  <svg :style="`width:${size};height:${size}`" viewBox="0 0 24 24">
    <path :fill="color" :d="name" />
  </svg>
</template>

<script lang="ts">
import { Vue, Prop, Component } from 'vue-property-decorator'

@Component
export default class Icon extends Vue {
  @Prop() readonly name!: string
  @Prop({default: '#a2aab0'}) readonly color!: string
  @Prop({default: '2rem'}) readonly size!: string
}
</script>

<style>
svg {
  cursor: pointer;
}
</style>