<template>
  <div id="app">
    <p v-on:click="changeText">{{message}}</p>
    <ul id="FRUKTER">
      <li v-for="item in Frukter" v-bind:key="item" v-on:click="moveFrukt(item)">{{item}}</li>
    </ul>

    <ul id="SALLAD">
      <li v-for="item in Sallad" v-bind:key="item">{{item}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    message: "Hello Vue!",
    index: 0,
    Frukter: ["Banan", "kiwi", "Päron"],
    Sallad: []
  }),

  methods: {
    changeText() {
      this.message = "Grillkorv";
    },

    moveFrukt(fruit) {
      console.log(fruit);
      this.Sallad.push(fruit);
      let index = this.Frukter.indexOf(fruit);
      this.Frukter.splice(index, 1);
      // Find index of fruit in this.Frukter
      // Splice the shit out of that index
    }
  }
};
</script>

<style>
#app {
  background-color: hotpink;
}
</style>