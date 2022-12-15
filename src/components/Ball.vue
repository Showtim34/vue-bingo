<template>
  <div :class="{selected: this.selected}" :id="'bouleRestante' + boule" class="move" :style="'top:' + top + 'px; right:'+right+'px'">
    <span class="boule" :style="'background: radial-gradient(circle at 100px 100px, #041a08, rgb(' + this.r + ', ' + this.g+', '+this.b+'));'">
      <em>
        <span v-if="boule<10">0</span>
        {{ this.boule }}
      </em>
    </span>
  </div>
</template>

<script>
//import { clearInterval } from 'timers';

export default {
  name: 'BallItem',
  props: ['boule', 'lastTirage'],
  data() {
    return {
      maxRight: 880,
      maxTop: 1000,
      top: null,
      right: null,

      x: true,
      y: true,

      moveX: 3,
      moveY: 3,

      r: null,
      g: null,
      b: null,
      interval: null,
      selected: false
    }
  },
  mounted() {
    this.init();
    this.interval = setInterval(() => {
      this.move();
    }, 60);
  },
  watch: {
    lastTirage: function() {
      
      if(this.lastTirage == this.boule) {
        clearInterval(this.interval)
        this.selected = true
      }
        
    }
  },
  unmounted() {
    clearInterval(this.interval);
  },

  methods: {
    move() {
      if (this.selected)
        return;

      if (this.y) {
        this.top = this.top + this.moveY
      } else 
        this.top = this.top - this.moveY
      
      if (this.x) 
        this.right = this.right + this.moveX
      else
        this.right = this.right - this.moveX

      if (this.top > this.maxTop) {
        this.y = false
        this.moveY = this.randomNumber(3, 10)
      } else if (this.top < 10) {
        this.y = true
        this.moveY = this.randomNumber(3, 10)
      }

      if (this.right > this.maxRight) {
        this.x = false
        this.moveX = this.randomNumber(3, 10)
      } else if (this.right < 10) {
        this.x = true
        this.moveX = this.randomNumber(3, 10)
      }
    },
    init() {
      this.top = this.randomNumber(10, this.maxTop)
      this.right = this.randomNumber(10, this.maxRight)

      this.moveY = this.randomNumber(3, 10)
      this.moveX = this.randomNumber(3, 10)

      this.r = this.randomNumber(0, 255)
      this.g = this.randomNumber(0, 255)
      this.b = this.randomNumber(0, 255)
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
<style>
.move {
  position: absolute;
  right: 0;
  top: 0;
}
.boule {
  display: inline-block;
  background: radial-gradient(circle at 100px 100px, #041a08, rgb(28, 197, 118));
  color: #fff;
  padding: 1rem;
  border-radius: 5rem;
  width: 54px;
  height: 54px;
  margin: 0.3rem;
  position: relative;
  z-index: 50;
}

.boule em {
  position: absolute;
  left: 6px;
  top: 6px;
  background: #fff;
  color: rgb(45, 122, 30);
  border-radius: 5rem;
  padding: 0.2rem;
  width: 33px;
  height: 33px;
  display: inline-block;
  font-weight: bold;
  font-size: 1.2rem;
  letter-spacing: -2px;
}

.move {
  scale: 1;
  transition: scale 3s, top 0.3s, right 0.3s;
}
.selected {
  scale: 10;
  z-index: 1000;
  right: 960px !important;
  top: 540px !important;
  
}

.selected .boule {box-shadow: #041a08 1px 1px 20px 5px; border: 3px solid #fff}
</style>
