<template lang="pug">
  .home
    upper-part
    lower-part
</template>

<script>
import debug from 'debug'
import LowerPart from '@/components/LowerPart'
import UpperPart from '@/components/UpperPart'
let log = debug('component:Home')
export default {
  name: 'home',
  props: [],
  data () {
    return {
    }
  },
  beforeCreate: function () {
  },
  mounted: function () {
    log('Mounted')
  },
  computed: {
  },
  methods: {
  },
  components: {
    'lower-part': LowerPart,
    'upper-part': UpperPart
  }
}
</script>

<style scoped lang="scss">
@import "../styles/_variables";

.home {
  position: relative;
  overflow: hidden;
  /* background: lightblue; */
  height: 1020px;
  @media #{$mobile} {
    height: auto;
  }
}
</style>
