<template>
  <div class="column q-gutter-md">
    <sample-position v-if="hasPosition" />
    <sample-geolocation-button />
    <geolocation-permission-banner />
  </div>
</template>

<script>
import { mapGeolocationGetters } from 'quasar-app-extension-geolocation/src/store'

import GeolocationPermissionBanner from './GeolocationPermissionBanner'
import SampleGeolocationButton from './SampleGeolocationButton'
import SamplePosition from './SamplePosition'

export default {
  components: {
    GeolocationPermissionBanner,
    SampleGeolocationButton,
    SamplePosition
  },
  data () {
    return {
    }
  },
  computed: {
    ...mapGeolocationGetters([
      'hasPosition'
    ])
  }
}
</script>
