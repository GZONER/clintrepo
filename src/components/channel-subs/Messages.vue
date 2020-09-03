<template>
  <v-card
    outlined
    height="100%"
    class="overflow-y-auto"
  >
    <v-list
        subheader
        two-line
        align="center"
        justify="center"
        style="max-height: 400px"
        disabled
      >
      <v-list-item-group>
          <v-list-item
            v-for="(message, index) in messages"
            :key="index"
          >
            <v-list-item-content>
              <v-list-item-subtitle>
                {{ message }}
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
      </v-list-item-group>
      </v-list>
  </v-card>
</template>

<script>
  export default {
    name: 'Messages',
    data: () => ({
      messages: [
        'System message: You must be at least 18 to join MelodyCam',
        'System message: Please verify your age to start chatting'
      ]
    })
  }
</script>

<style lang="scss" scoped>

</style>