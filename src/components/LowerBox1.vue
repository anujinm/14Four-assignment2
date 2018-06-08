<template lang="pug">
  .lowerBox
    img(src='../../clipboard.svg')
    h5 Overview
    p skj lksfjns slfn aksdghbesd iuahkbd.. 
    button Learn More
    </style>
    
</template>

<script>
import debug from 'debug'
let log = debug('component:LowerBox1')
export default {
  name: 'lowerBox1',
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
  }
}
</script>

<style scoped lang="scss">
.lowerBox {
  background: white;
}
</style>
