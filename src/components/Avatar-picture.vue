<template>
  <div class="avatar-container">
    <img v-if="this.rand == 0" src="@/assets/selfie/nico-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 0" src="@/assets/selfie/nico-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 1" src="@/assets/selfie/younes-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 1" src="@/assets/selfie/younes-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 2" src="@/assets/selfie/serge-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 2" src="@/assets/selfie/serge-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 3" src="@/assets/selfie/maela-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 3" src="@/assets/selfie/maela-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 4" src="@/assets/selfie/lolita-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 4" src="@/assets/selfie/lolita-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 5" src="@/assets/selfie/laurent-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 5" src="@/assets/selfie/laurent-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 6" src="@/assets/selfie/juju-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 6" src="@/assets/selfie/juju-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 7" src="@/assets/selfie/jessica-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 7" src="@/assets/selfie/jessica-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 8" src="@/assets/selfie/eric-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 8" src="@/assets/selfie/eric-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 9" src="@/assets/selfie/clementvieux-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 9" src="@/assets/selfie/clementvieux-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 10" src="@/assets/selfie/clementsapin-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 10" src="@/assets/selfie/clementsapin-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 11" src="@/assets/selfie/clementlunette-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 11" src="@/assets/selfie/clementlunette-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 12" src="@/assets/selfie/clementbonnet-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 12" src="@/assets/selfie/clementbonnet-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 13" src="@/assets/selfie/caro-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 13" src="@/assets/selfie/caro-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 14" src="@/assets/selfie/camille-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 14" src="@/assets/selfie/camille-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img v-if="this.rand == 15" src="@/assets/selfie/lola-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 15" src="@/assets/selfie/lola-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />

    <img v-if="this.rand == 16" src="@/assets/selfie/lucie-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 16" src="@/assets/selfie/lucie-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />

    <img v-if="this.rand == 17" src="@/assets/selfie/romain-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 17" src="@/assets/selfie/romain-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />

    <img v-if="this.rand == 18" src="@/assets/selfie/serge2-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img v-if="this.rand == 18" src="@/assets/selfie/serge2-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />

    <img src="@/assets/danse.webp" class="img-fluid danse" />
  </div>
</template>

<script>
//import { clearInterval } from 'timers';

export default {
  name: 'AvatarPicture',
  props: ['state', 'change'],
  data() {
    return {
      img: '',
      rand: 0,
    }
  },
  watch: {
    change: function () { // watch it
      setTimeout( () => {
          this.rand = this.randomNumber();
        }, 3000)
      } 
  },
  mounted() {
    this.rand = this.randomNumber();
  },
 
  unmounted() {
    
  },

  methods: {
    randomNumber() {
      return Math.floor(Math.random() * (19));
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.avatar-container {width: 280px; position: relative; margin:0 auto; height: 400px;}
.avatar-container img {position:absolute; left : 0}
.top { top: 0px;  z-index:10; }
.bottom { top: 320px;   z-index:9; }
.danse { top: 300px; left: 50px; z-index:5;}

.top.breathe {animation: 0.6s linear .1s infinite alternate breatheTop;}
.bottom.breathe {animation: .5s linear .1s infinite alternate breatheBottom;}


.top.talk {animation: 0.3s linear 0.1s infinite alternate talkTop;}
.bottom.talk {animation: 0.3s linear 0.1s infinite alternate talkBottom;}

@keyframes talkTop {
  0% {
    top: 0px;
    transform: rotate(0);
  }
  100% {
    top: -40px;
    transform: rotate(2deg);
  }
}

@keyframes talkBottom {
  0% {
    top: 320px;
  }
  100% {
    top: 310px;
    transform: rotate(2deg);
  }
}

@keyframes breatheTop {
  0% {
    top: 0px;
    transform: rotate(0);
  }
  100% {
    top: -3px;
    transform: rotate(2deg);
  }
}

@keyframes breatheBottom {
  0% {
    top: 320px;
  }
  100% {
    top: 330 px;
    transform: rotate(2deg);
  }
}

</style>
