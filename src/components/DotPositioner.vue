<template>
  <svg>
      <circle :cx="x" :cy="y" :r="radius" />
  </svg>
</template>

<script>
export default {
    props:{
        x: Number,
        y: Number,
        radius: Number,
    }
}
</script>

<style>

</style>