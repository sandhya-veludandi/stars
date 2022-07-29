<script lang="ts">
import Particles from './components/Particles.vue'
import { defineComponent } from 'vue'

export default defineComponent({
  components: {
    Particles
  }
})
</script>

<template>
  <Particles />
</template>

<style>
body {
  margin: 0;
  padding: 0;
}
</style>
