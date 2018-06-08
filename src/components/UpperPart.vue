<template lang="pug">
  .upper
    .triangles
      img.triangle1(src='../../triangle1.svg')
      img.triangle2(src='../../triangle1.svg')
      img.triangle3(src='../../triangle1.svg')
      img.triangle4(src='../../triangle1.svg')
    .links
      i.fab.fa-facebook-f
      i.fab.fa-twitter
      i.fab.fa-linkedin-in
    upperText.textBox
    img.laptop(src='../../ipad.svg')
    img.message(src='../../message.svg')
    p.video PLAY VIDEO &nbsp; &mdash;
    .circleBlue
    .circleGray
</template>

<script>
import debug from 'debug'
import upperText from '@/components/UpperText'
let log = debug('component:UpperPart')
export default {
  name: 'upper',
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
    'upperText': upperText
  }
}
</script>

<style scoped lang="scss">
@import "../styles/_variables";
.upper {
  .links {
    position: absolute;
    transform: rotate(90deg);
    transform-origin: left top 0;
    color: white;
    top: 45%;
    left: 10%;
    font-size: 15px;
    i {
      padding: 10px;
      transform: rotate(270deg);
      transform-origin: left top 0;
    }
  }
  .textBox {
    width: 100%;
    height: 100%;
    top: 25%;
    left: 20%;
    position: absolute;
  }
  .triangles {
    opacity: 0.3;
    .triangle1 {
      left: 3%;
      top: 50%;
      width: 30%;
      height: 30%;
      position: absolute;
    }
    .triangle2 {
      left: 9%;
      top: 45%;
      width: 30%;
      height: 30%;
      position: absolute;
    }
    .triangle3 {
      left: 55%;
      top: 20%;
      width: 20%;
      height: 20%;
      position: absolute;
    }
    .triangle4 {
      left: 60%;
      top: 15%;
      width: 15%;
      height: 15%;
      position: absolute;
    }
  }
  .laptop {
    position: absolute;
    width: 40%;
    height: 40%;
    top: 30%;
    left: 50%;
  }
  .message {
    position: absolute;
    width: 4%;
    height: 4%;
    top: 38%;
    left: 66%;
  }
  .video {
    color: gray;
    font-size: 10px;
    letter-spacing: 2px;
    transform: rotate(90deg);
    transform-origin: left top 0;
    position: absolute;
    left: 90%;
    top: 38%;
  }
  .circleBlue {
    border-radius: 50%;
    width: 210%;
    height: 250%;
    background: linear-gradient($main-purple, $main-blue);
    position: absolute;
    top: -150%;
    left: -110%; 
    z-index: -1;
    overflow: hidden;
  }
  .circleGray {
    border-radius: 50%;
    width: 210%;
    height: 210%;
    background: #EBEBEB;
    position: absolute;
    top: -113%;
    left: -100%; 
    z-index: -2;
    overflow: hidden;
  }
  position: relative;
  overflow: hidden;
  height: 18em;
  @media #{$mobile} {
    .laptop {
      top:60%;
      left: 20%
    }
    .message {
      top:75%;
      left: 34%
    }
    .video {
      font-size: 5px;
      top:73%;
      left: 65%
    }
  }
}
</style>
