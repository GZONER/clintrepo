<template>
  <!-- <v-container fluid> -->
  <v-row justify="center">
    <v-col cols="12">
      <switches :userTypes="userTypes" @send-user-type="filterchoice" />
    </v-col>

    <!-- nested row (depth1) -->
    <v-row>
      <v-col :cols="$vuetify.breakpoint.xsOnly ? 12 : 6">
        <cam-preview class="mb-4">
          <template #overlay>
            <ButtonModal color="grey" fab :src="require('@/assets/settings.svg')" rounded />
            <ButtonModal :btnName="`Searching for ${currentType}`" btnIcon="play" rounded small />
          </template>
        </cam-preview>

        <cam-preview>
          <template #overlay>
            <ButtonModal color="grey" fab btnIcon="microphone" rounded small />
            <ButtonModal color="grey" fab btnIcon="video" rounded small />
          </template>
        </cam-preview>
      </v-col>

      <v-col :cols="$vuetify.breakpoint.xsOnly ? 12 : 6">
        <messages />
      </v-col>
    </v-row>
  </v-row>
</template>

<script>
  import Messages from './channel-subs/Messages.vue'
  import CamPreview from './channel-subs/CamPreview.vue'
  import Switches from './channel-subs/Switches.vue'
  import ButtonModal from './shared/ButtonModal.vue'
  export default {
    components: {
      ButtonModal,
      Switches,
      CamPreview,
      Messages
    },
    data() {
      return {
        showModal: false,
        overlay: true,
        currentType: 'Female',
        userTypes: [
          'Female',
          'Male',
          'Couple'
        ]
      }
    },
    methods: {
      filterchoice: function (u) {
        this.currentType = u;
      },
    }
  }
</script>

<style lang="css" scoped>
  .my-overlay .v-overlay__content {
    height: '100%';
  }
</style>