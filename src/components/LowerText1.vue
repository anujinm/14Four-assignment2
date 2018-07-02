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
  font-family: 'Roboto';
  text-align: center;
  p {
    font-size: 15px;
    letter-spacing: 1px;
    color: #2611C9;
  }
  h5 {
    font-size: 27px;
    margin-bottom: 5px;
    background: -webkit-linear-gradient(#4762E2, #2611C9);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  @media #{$mobile} {
    h5 {font-size: 15px;}
    p {font-size: 15px;}
  }
}
</style>
