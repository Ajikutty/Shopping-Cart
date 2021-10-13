<template>
  <div class="main">
    <div class="header">&nbsp;<i class="fab fa-apple"></i> Shop Mac...</div>
    <button v-on:click="goToCart()" class="cartitemheader">
      <i class="fas fa-shopping-cart"></i> <p> {{ cartcounter(c1, c2) }} </p>
    </button>
  </div>
  <div class="container">
    <div class="box">
      <img
        src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/macbook-air-space-gray-select-201810?wid=452&hei=420&fmt=jpeg&qlt=95&.v=1603332211000"
      />
      <h1 class="boxh1">
        Apple M1 Chip with <br />
        8‑Core CPU and <br />
        7‑Core GPU <br />
        256GB Storage
      </h1>
      <p class="boxp">
        Apple M1 chip with 8‑core CPU, 7‑core GPU <br />
        and 16‑core Neural Engine <br /><br />
        8GB unified memory <br /><br />
        256GB SSD storage¹ <br /><br />
        Retina display with True Tone <br /><br />
        Magic Keyboard <br /><br />
        Touch ID <br /><br />
        Force Touch trackpad <br /><br />
        Two Thunderbolt / USB 4 ports
      </p>
      <h2 class="boxh2">
        From ₹10934/mo. <br />
        with EMI,**
      </h2>
      <p class="boxp1">or</p>
      <h3 class="boxh3">₹92900</h3>
      <button class="boxbutton" v-on:click="increase">ADD TO CART</button>
      <br><br>
      <div class="button-arranging">
      <button class="boxbutton1" v-on:click="decrease">-</button>
      <h1 class="boxbutton2">{{ counter}}</h1>
      <button class="boxbutton3" v-on:click="increase">+</button>
      </div>
    </div>
    <div class="box">
      <img
        src="https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/macbook-air-gold-select-201810?wid=452&hei=420&fmt=jpeg&qlt=95&.v=1603332211000"
      />
      <h1 class="boxh1">
        Apple M1 Chip with <br />
        8‑Core CPU and <br />
        8‑Core GPU <br />
        512GB Storage
      </h1>
      <p class="boxp">
        Apple M1 chip with 8‑core CPU, 8‑core GPU and 16‑core Neural Engine
        <br /><br />
        8GB unified memory <br /><br />
        512GB SSD storage¹ <br /><br />
        Retina display with True Tone <br /><br />
        Magic Keyboard <br /><br />
        Touch ID <br /><br />
        Force Touch trackpad <br /><br />
        Two Thunderbolt / USB 4 ports
      </p>
      <h2 class="boxh2">
        From ₹13876/mo. <br />
        with EMI,**
      </h2>
      <p class="boxp1">or</p>
      <h3 class="boxh3">₹117900</h3>
      <button class="boxbutton" v-on:click="plus">ADD TO CART</button>
      <br><br>
      <div class="button-arranging">
      <button class="boxbutton1" v-on:click="mines">-</button>
      <h1 class="boxbutton2">{{ counter1 }}</h1>
      <button class="boxbutton3" v-on:click="plus">+</button>
      </div>
    </div>
  </div>
  <div class="totalamount">TOTAL = ₹{{ total(t1, t2) }}</div>
  <button class="totalreset" v-on:click="reset(goout1, goout2)">RESET</button>
  <hr />
</template>
<script>
export default {
  name: "App",
  data: () => {
    return {
      counter: 0,
      counter1: 0,
    };
  },
  methods: {
    increase: function () {
      this.counter++;
    },
    decrease: function () {
      if (this.counter > 0) {
        this.counter--;
      }
    },
    goout1: function () {
      this.counter = 0;
    },
    goout2: function () {
      this.counter1 = 0;
    },
    reset: function (goout1, goout2) {
      goout1();
      goout2();
    },
    plus: function () {
      this.counter1++;
    },
    mines: function () {
      if (this.counter1 > 0) {
        this.counter1--;
      }
    },
    c1: function () {
      this.counter;
    },
    c2: function () {
      this.counter1;
    },
    cartcounter: function () {
      return this.counter + this.counter1;
    },
    t1: function () {
      return this.counter * 92900;
    },
    t2: function () {
      return this.counter1 * 117900;
    },
    total: function (t1, t2) {
      return t1() + t2();
    },

    goToCart(){
      this.$router.push('/cart')
    }

  },
};
</script>
<style scoped>
</style>
