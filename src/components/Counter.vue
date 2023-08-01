<template>
  <h2>{{ getTitle }}</h2>
  <p>{{ counter }} <sup>2</sup> = {{ squareCounter }}</p>
  <div>
    <button @click="decrease">-1</button>
    <button @click="increase">+1</button>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    start: {
      type: Number,
      default: 5,
      validator(value) {
        return value > 100
      }
    },
  },
  data() {
    return {
      counter: 5,
    };
  },
  methods: {
    getSquareValue() {
      console.log("xD");
      return this.counter * this.counter;
    },
    increase() {
      this.counter++;
    },
    decrease() {
      this.counter--;
    },
  },
  computed: {
    squareCounter() {
      console.log("xdxd");
      return this.counter * this.counter;
    },
    getTitle() {
      return this.title || "Salieron";
    },
  },
};
</script>

<style>
button {
  background-color: #222;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}
button:hover {
  background-color: #333;
  transition: 0.3s ease-in-out;
}
</style>