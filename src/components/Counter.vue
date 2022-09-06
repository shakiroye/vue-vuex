<script>
import { mapState, mapMutations, mapActions } from "vuex";
export default {
  data() {
    return {
      value: 1,
    };
  },

  computed: {
    ...mapState(["counter"]),
  },

  methods: {
    ...mapMutations(["addToCounter", "substractFromCounter"]),
    ...mapActions(["addRandomNumber"]),
  },
};
</script>


<template>
  <div>
    <h1>VueX Counter</h1>
    <h1 class="counter">{{ counter }}</h1>
    <button @click="substractFromCounter(value)">-</button>
    <input type="number" v-model="value" />
    <button @click="addToCounter(value)">+</button>
    <div>
      <button class="btn" @click="addRandomNumber">Add By Random Number</button>
    </div>
  </div>
</template>

<style>
.counter {
  font-size: 5rem;
}
button {
  border-radius: 100%;
  border: none;
  width: 2rem;
  height: 2rem;
  cursor: pointer;
}

.btn {
  border-radius: 00.5rem;
  width: auto;
  background-color: #41b983;
  margin-top: 1rem;
  color: white;
  cursor: pointer;
}

input {
  background-color: transparent;
  border: 1px white solid;
  padding: 0.4rem;
  margin: 0 0.5rem;
  text-align: center;
  color: white;
}
</style>
 