<template>
  <v-card height="250" min-width="300">
    <v-overlay
      :value="true"
      absolute
    >
      <slot name="overlay" />
    </v-overlay>
  </v-card>
</template>

<script>
  export default {
    name: 'CamPreview'
  }
</script>

<style lang="scss" scoped>

</style>