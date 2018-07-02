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
    img.mouse(src='../../mouse.svg')
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
  font-family: 'Roboto', sans-serif;
  .triangles {
    // background: linear-gradient(#c7c7c7, #202020);
    filter: brightness(20%);
    position: absolute;
    top: -5%;
    width: 100%;
    height: 100%;
    opacity: 0.5;
    .triangle1 {
      left: 3%;
      top: 66%;
      width: 23%;
      height: 23%;
      position: relative;
      margin-left: 40px;
      // margin-top: 20x;
      // margin-bottom: -20px;
    }
    .triangle2 {
      left: -15%;
      top: 58%;
      width: 23%;
      height: 23%;
      position: relative;
    }
    .triangle3 {
      left: 5%;
      top: 26%;
      width: 20%;
      height: 20%;
      position: relative;
    }
    .triangle4 {
      left: -7%;
      top: 10%;
      width: 8%;
      height: 8%;
      position: relative;
    }
  }
  .links {
    position: absolute;
    transform: rotate(90deg);
    transform-origin: left top 0;
    color: white;
    top: 56%;
    left: 11%;
    font-size: 13px;
    i {
      padding: 10px;
      transform: rotate(270deg);
      transform-origin: left top 0;
    }
  }
  .textBox {
    width: 100%;
    height: 100%;
    top: 28%;
    left: 20%;
    position: absolute;
  }
  .mouse {
    position: absolute;
    top: 70%;
    left: 50%;
    width: 18px;
  }
  .laptop {
    position: absolute;
    width: 34%;
    height: 34%;
    top: 32%;
    left: 53%;
  }
  .message {
    position: absolute;
    width: 5%;
    height: 5%;
    top: 40%;
    left: 65%;
  }
  .video {
    color: #a8a8a8;
    font-size: 10px;
    letter-spacing: 2px;
    transform: rotate(90deg);
    transform-origin: left top 0;
    position: absolute;
    left: 88%;
    top: 38%;
    width: 100%;
  }
  .circleBlue {
    border-radius: 50%;
    width: 200%;
    height: 270%;
    background: linear-gradient(to bottom right ,$main-purple, $main-blue);
    position: absolute;
    top: -170%;
    left: -97%;
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
  height: 600px;
  @media #{$mobile} {
    .textBox {
      top: 10%;
    }
    .mouse {
      top: 50%;
    }
    .laptop {
      top: 50%;
      left: 18%
    }
    .message {
      top:61%;
      left: 29%;
    }
    .video {
      font-size: 5px;
      top: 61%;
      left: 56%
    }
  }
  @media screen and (min-width: 1600px) {
    .mouse { left: 40%; }
    .laptop{
      left: 33%;
    }
    .message{
      left: 46%;
    }
    .video{
      left: 60%
    }
  }
}
</style>
