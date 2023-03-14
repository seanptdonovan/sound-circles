<template>
  <div class="home">
    
   
    <sound-circle id="circ1" class="circle" 
    @mouseover.native="playSound('one.mp3')" 
    />

    <sound-circle id="circ2" class="circle"
    @mouseover.native="playSound('two.mp3')"
    />
    <sound-circle id="circ3" class="circle"
    @mouseover.native="playSound('three.mp3')"
    />
    <span>
    <sound-circle id="circ4" class="circle"
    @mouseover.native="playSound('four.mp3')"
    />
    </span>
  </div>
</template>

<script>

import SoundCircle from '@/components/SoundCircle.vue';


export default {
  name: 'HomeView',
  data() {
    return {
      hover: false,
      playbackSpeed: 1,
      randomNumber: Math.floor(Math.random() * 1000) + "px",
    };
  },
  components: {
    SoundCircle,
  },
  methods: {
    playSound(fileName) {
      const audio = new Audio(require('../audio/' + fileName));
      audio.playbackRate = this.playbackSpeed;
      audio.play();
    },
   getRandomNumber(){
    return Math.floor(Math.random() * 1000) + "px"

   },
    keyDownHandler(e) {
        console.log(e.key)
        if (e.key == 1){this.playbackSpeed = .1}
        if (e.key == 2){ this.playbackSpeed = .2}
        if (e.key == 3){ this.playbackSpeed = .3}
        if (e.key == 4){ this.playbackSpeed = .4}
        if (e.key == 5){ this.playbackSpeed = .5}
        if (e.key == 6){ this.playbackSpeed = .6}
        if (e.key == 7){ this.playbackSpeed = .7}
        if (e.key == 8){ this.playbackSpeed = .8}
        if (e.key == 9){ this.playbackSpeed = .9}
       
        if (e.key == '@'){ this.playbackSpeed = 2}
        if (e.key == '#'){ this.playbackSpeed = 4}
        if (e.key == '$'){ this.playbackSpeed = 6}
        if (e.key == '%'){ this.playbackSpeed = 8}
        if (e.key == '^'){ this.playbackSpeed = 10}
        if (e.key == '&'){ this.playbackSpeed = 12}
        if (e.key == '*'){ this.playbackSpeed = 14}
        if (e.key == '('){ this.playbackSpeed = 16}
    },
    keyUpHandler(e) {
        console.log(e.key)
        if (e.key == 1){this.playbackSpeed = 1}
        if (e.key == 2){ this.playbackSpeed = 1}
        if (e.key == 3){ this.playbackSpeed = 1}
        if (e.key == 4){ this.playbackSpeed = 1}
        if (e.key == 5){ this.playbackSpeed = 1}
        if (e.key == 6){ this.playbackSpeed = 1}
        if (e.key == 7){ this.playbackSpeed = 1}
        if (e.key == 8){ this.playbackSpeed = 1}
        if (e.key == 9){ this.playbackSpeed = 1}
    
        if (e.key == '@'){ this.playbackSpeed = 1}
        if (e.key == '#'){ this.playbackSpeed = 1}
        if (e.key == '$'){ this.playbackSpeed = 1}
        if (e.key == '%'){ this.playbackSpeed = 1}
        if (e.key == '^'){ this.playbackSpeed = 1}
        if (e.key == '&'){ this.playbackSpeed = 1}
        if (e.key == '*'){ this.playbackSpeed = 1}
        if (e.key == '('){ this.playbackSpeed = 1}
    },


//////// Random Animate








},
created() {
    window.addEventListener('keydown', this.keyDownHandler),
    window.addEventListener('keyup', this.keyUpHandler)

},
destroyed() {
    window.removeEventListener('keydown', this.keyDownHandler),
    window.removeEventListener('keyup', this.keyUpHandler)
    
},
};

</script>

<style>

div{
  display: flex;
}

.circle {
  margin-top: 50px;
}

#circ1 {
  animation: test1;
  animation-duration: 7s;
  animation-iteration-count: infinite;
  background-color: #FFA83B;
  display: flex;
}

@keyframes test1{
  0%{
    margin-top: 0px;
  }
  15%{
    margin-top: v-bind(getRandomNumber());
  }
  22% {
    margin-right: v-bind(getRandomNumber())
  }
}

#circ2 {
  animation: test2;
  animation-duration: 7s;
  animation-iteration-count: infinite;
  background-color: #C35421;
  display: flex;
}

@keyframes test2 {
  0%{
    margin-top: 0px;
  }
  50%{
    margin-left: 200px;
  }
  100%{
    margin-top: 200px;
  }
}

#circ3 {
  animation: test3;
  animation-duration: 4s;
  animation-iteration-count: infinite;
  background-color: #F88279;
  display: flex;
}

@keyframes test3 {
  0%{
    margin-top: 0px;
  }
  75%{
    margin-right: 400px;
  }
  100%{
    margin-top: 200px;
  }
}

#circ4 {
  animation: test4;
  animation-duration: 40s;
  animation-iteration-count: infinite;
  background-color: #9968AA;
  display: flex;
}

@keyframes test4 {
  0%{
    margin-top: 0px;
  }
  50%{
    margin-top: 500px;
  }
  0%{
    margin-top: 0px;
  }
}

</style>
