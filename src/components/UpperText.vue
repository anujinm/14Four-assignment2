<template lang="pug">
  .upperText
    p.t5 - What we do
    h5 Providing the 
    h5 best customer service 
    p.t5.low Spicy jalapeno bacon ipsum dolor amet do prosciutto pork. Meatball short loin in aliqua. 
    button Learn More &nbsp; &#8594;   
</template>

<script>
import debug from 'debug'
let log = debug('component:UpperText')
export default {
  name: 'upperText',
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
@import "../styles/_variables";
.upperText {
  max-width: 300px;
  max-height: 400px;
  color: white;
  h5 {
    margin-bottom: 10px;
    line-height: 25px;
  }
  p {
    font-size: 15px;
    padding-top: 10px;
    padding-bottom: 20px;
    &.low{
      line-height: 20px;
      padding-bottom: 30px;
    }
  }
  button {
    color: #2611C9;
    font-size: 12px;
    padding: 12px;
    border-radius: 3px;
  }
  @media #{$mobile} {
    h5 {font-size: 20px;}
    p {font-size: 10px; max-width: 150px;}
    button {
      font-size: 10px;
    }
  }
}
</style>
