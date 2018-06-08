<template lang="pug">
  .lowerText
    h5 {{ number }}
    p {{ word }}
</template>

<script>
import debug from 'debug'
let log = debug('component:LowerText1')
export default {
  name: 'lowerText1',
  props: [
    'number',
    'word'
  ],
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
  }
}
</script>

<style scoped lang="scss">
@import "../styles/_variables";
.lowerText {
  background: transparent;
  color: blue;
  text-align: center;
  p {
    font-size: 20px;
  }
  h5 {
    margin: 0;
  }
  @media #{$mobile} {
    h5 {font-size: 15px;}
    p {font-size: 15px;}
  }
}
</style>
