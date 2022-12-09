<template>
  <div id="waiting" :class="{'hide' : this.gameStarted}"></div>
  <div id="quine" :class="{
    'hide' : ! this.quine, 
    'q1': this.quineClass == 'q1',
    'q2': this.quineClass == 'q2',
    'q3': this.quineClass == 'q3',
    'q4': this.quineClass == 'q4',
    'q5': this.quineClass == 'q5',
    'q6': this.quineClass == 'q6',
    'q7': this.quineClass == 'q7',
    'q8': this.quineClass == 'q8',
    'q9': this.quineClass == 'q9',
    'q12': this.quineClass == 'q12',
    'q13': this.quineClass == 'q13',
    'q14': this.quineClass == 'q14',
    'q15': this.quineClass == 'q15',
    'q16': this.quineClass == 'q16'

  }" ref="quineLayer"></div>
  <div class="row" v-if="this.gameStarted">
    <div class="col-6 text-center">
      <AvatarPicture :state="this.state"></AvatarPicture>
      <div class="row listBoules">
        <div class="col-1" v-for="(boule) in boules" :key="boule">
          <div class="boule">
            <em><span v-if="boule<10">0</span>{{boule}}</em>
          </div>
        </div>
      </div>

    </div>
    <div class="col-6 restantes">
      <Ball v-for="(restant) in this.restants" :key="restant" :id="'bouleRestante' + restant" :boule="restant" :lastTirage="this.lastTirage"></Ball>
    </div>


  </div>
</template>

<script>
import Ball from './Ball.vue'
import AvatarPicture from './Avatar-picture.vue'

export default {
  name: 'LottoApp',
  components: { Ball, AvatarPicture },
  data() {
    return {
      gameStarted: false,
      boules: [],
      restants: [],
      lastTirage: null,

      state: 'breathe',
      quine: false,
      quineClasses:['q1', 'q2', 'q3', 'q4', 'q5', 'q6', 'q7', 'q8', 'q9', 'q12', 'q13', 'q14', 'q15', 'q16'],
      quineClass: '',

      numbers: 17
    }
  },

  created() {

    window.addEventListener('keydown', (e) => {
      if (e.key == 'Escape') {
        this.gameStarted = false
      }

      if (e.key == 'Enter') {
        this.setQuine()
      }

      if (e.key == ' ') {

        if (! this.gameStarted)
          this.initGame()
          else
          this.tirage();
      }

    });
  },

  mounted() {
    
  },

  methods: {
    setQuine()
    {
      this.quine = ! this.quine
      if (this.quine) {
        this.playSound("/numbers/victoire.mp3")
        this.quineClass = this.quineClasses[Math.floor(Math.random()*this.quineClasses.length)]
        this.$refs.quineLayer.classList.add(this.quineClass)
      } else {
        this.$refs.quineLayer.classList.remove(this.quineClass)
      }

      
    },

    initGame() {
      this.gameStarted = true;
      let i = 1
      while (this.restants.length != this.numbers) {
        this.restants.push(i);
        i++
      }
    },

    tirage() {
      let exists = true;
      let rand;
      while (exists) {
        rand = this.randomNumber(1, this.numbers + 1);
        console.log("-", rand)
        exists = this.boules.includes(rand);
      }

      this.boules.push(rand)
      //this.boules.sort()

      //this.boules.reverse()
      
      this.state = 'talk'
      this.playSound("/numbers/"+rand+".m4a")



      setTimeout(() => {
        this.state = 'breathe'
        this.lastTirage = rand
      }, 3000);

      setTimeout(() => {
        let tmp = []
        this.restants.forEach(n => {
          if (n != rand)
            tmp.push(n)
        })
        this.restants = tmp
      }, 6000);

    },

    playSound (sound) {
      if(sound) {
        var audio = new Audio(sound);
        audio.play();
      }
    },

    randomNumber(min, max) {
      return Math.floor(Math.random() * (max - min)) + min;
    },
    sleep(ms) {
      return new Promise((resolve) => {
        setTimeout(resolve, ms);
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.restantes {
  height: 100vh;
  background: rgba(15, 15, 15, 0.219)
}

#waiting {
  background:url("@/assets/loto.jpg") no-repeat center center fixed;
  width: 1920px;
  height: 1080px;
  background-size: cover ;
  position: absolute;
  top:0;
  left:0;
  transition: height 1s;
  z-index: 100;
}
#waiting.hide {
  height: 0vh;
}

#quine {
  width: 1920px;
  height: 1080px;
  position: absolute;
  top:0;
  left:0;
  transition: height 1s;
  z-index: 100;
}
#quine.q1 {
  background:url("@/assets/quine-1.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q2 {
  background:url("@/assets/quine-2.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q3 {
  background:url("@/assets/quine-3.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q4 {
  background:url("@/assets/quine-4.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q5 {
  background:url("@/assets/quine-5.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q6 {
  background:url("@/assets/quine-6.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q7 {
  background:url("@/assets/quine-7.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q8 {
  background:url("@/assets/quine-8.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q9 {
  background:url("@/assets/quine-9.webp") no-repeat center center fixed;
  background-size: cover ;
}


#quine.q12 {
  background:url("@/assets/quine-12.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q13 {
  background:url("@/assets/quine-13.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q14 {
  background:url("@/assets/quine-14.gif") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q15 {
  background:url("@/assets/quine-15.webp") no-repeat center center fixed;
  background-size: cover ;
}

#quine.q16 {
  background:url("@/assets/quine-16.webp") no-repeat center center fixed;
  background-size: cover ;
}


#quine.hide {
  height: 0vh;
}

.listBoules {margin-top: 165px;}
</style>
