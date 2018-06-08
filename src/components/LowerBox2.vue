<template lang="pug">
  .lowerBox
    img(src='../../target.svg')
    h5 Audience
    p skj lksfjns slfn aksdghbesd iuahkbd.. 
    button Learn More
    </style>
    
</template>

<script>
import debug from 'debug'
let log = debug('component:LowerBox2')
export default {
  name: 'lowerBox2',
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
