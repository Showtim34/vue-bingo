<template>
  <div class="avatar-container">
    <img src="@/assets/nico/nico-1.png" class="img-fluid top" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}"/>
    <img src="@/assets/nico/nico-2.png" class="img-fluid bottom" v-bind:class="{'talk': this.state == 'talk', 'breathe': this.state == 'breathe'}" />
    <img src="@/assets/danse.webp" class="img-fluid danse" />
  </div>
</template>

<script>
//import { clearInterval } from 'timers';

export default {
  name: 'AvatarPicture',
  props: ['state'],
  data() {
    return {
      
    }
  },
  mounted() {
    
  },
 
  unmounted() {
    
  },

  methods: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.avatar-container {width: 280px; position: relative; margin:0 auto; height: 400px;}
.avatar-container img {position:absolute; left : 0}
.top { top: 0px;  z-index:10}
.bottom { top: 320px;   z-index:9}
.danse { top: 330px; left: 50px; z-index:5;}

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
