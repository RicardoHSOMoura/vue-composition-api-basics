<template>
  <div class="home">

    <h2>{{ appTitle }}</h2>

    <h3>{{ counterData.title }}:</h3>
   
    <div>
    <button @click="decreaseCounter" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="increaseCounter" class="btn">+</button>
   </div>
  </div>

  <div class="edit">
    <h4>Edit counter title:</h4>
    <input v-model="counterData.title" type="text">
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const appTitle = 'My Amazing Counter App'

// const counter = ref(0), 
//       counterTitle = ref('My Counter')

const counterData = reactive({
  count: 0,
  title: 'My Counter'
})

const increaseCounter = () => {
  counterData.count++
}

const decreaseCounter = () => {
  counterData.count--
}
</script>


<!--

COMPOSITION API without SCTIPT SETUP
<script>
import { ref } from 'vue'
export default {
  setup() {
    const counter = ref(0)

    const increaseCounter = () => counter.value++;

    const decreaseCounter = () => counter.value--;

    return {
      counter,
      increaseCounter,
      decreaseCounter
    }
  }
}
</script>

OPTIONS API

<script>
export default {
  data() {
    return {
      counter: 0,
    }
  },
  methods: {
    increaseCounter() {
      this.counter++;
    },
    decreaseCounter() {
      this.counter--;
    }
  }
}
</script>
-->

<style>
.home {
  text-align: center;
  padding: 20px;
}
.btn, .counter {
  font-size: 40px;
  margin: 10px;
}
.edit {
  text-align: center;
}
</style>
