<template lang="pug">
  .lowerBox
    img(src='../../skills.svg')
    h5 Competitors
    p skj lksfjns slfn aksdghbesd iuahkbd.. 
    button Learn More
    </style>
    
</template>

<script>
import debug from 'debug'
let log = debug('component:LowerBox3')
export default {
  name: 'lowerBox3',
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
  button {
    border: 1px solid white;
  }
  background: #2936B5;
}
</style>
