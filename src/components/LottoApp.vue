<template>
  <div id="waiting" :class="{'hide' : this.gameStarted}" @click="initGame"></div>
  <div class="row" v-if="this.gameStarted">
    <div class="col-6 text-center">
      <img src="https://i.pravatar.cc/300" class="avatar mb-5 mt-5"><br>
      <button @click="this.tirage" class="btn btn-primary">Tirage d'une boule</button>

      <div class="row">
        <div class="col-1" v-for="(boule) in boules" :key="boule">
          <div class="boule">
            <em>{{boule}}</em>
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
export default {
  name: 'LottoApp',
  components: { Ball },
  data() {
    return {
      gameStarted: false,
      boules: [],
      restants: [],
      lastTirage: null
    }
  },
  mounted() {
    
  },

  methods: {
    initGame() {
      this.gameStarted = true;
      let i = 1
      while (this.restants.length != 90) {
        this.restants.push(i);
        i++
      }
    },

    tirage() {
      let exists = true;
      let rand;
      while (exists) {
        rand = this.randomNumber(1, 90);
        exists = this.boules.includes(rand);
      }
      this.lastTirage = rand
      this.boules.push(rand)
      //this.boules.reverse()

      setTimeout(() => {
        let tmp = []
        this.restants.forEach(n => {
          if (n != rand)
            tmp.push(n)
        })
        this.restants = tmp
      }, 6000);

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
</style>
