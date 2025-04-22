<script setup lang="ts">
 import { ref , computed} from 'vue'
 const counter = ref<number>(0);

 // Increment function
function incrementCounter(){
   counter.value ++
}
 // Double Increment function
function doubleIncrementCounter(){
   counter.value += 2
}

 // Decrement function
function decrementCounter(){
  if(counter.value > 0)
   counter.value --
}

// Double Decrement function
function doubleDecrementCounter(){
  if(counter.value > 0)
   counter.value -= 2
}

function reset(){
   counter.value = 0
}
const oddEven = computed(() => {
  const isEven = counter.value % 2 === 0
  return {
    label: isEven ? 'Even' : 'Odd',
    className: isEven ? 'even' : 'odd'
  }
})
</script>

<template>
  <div class="container">
  <h1>Counter App</h1>
  <h2 :class="oddEven.className">{{ counter }}</h2>
  <h3>Number is {{ oddEven.label }}</h3>
  <div>
    <button @click="decrementCounter">-</button>
    <button @click="doubleDecrementCounter">-2</button>
    <button @click="incrementCounter">+</button>
    <button @click="doubleIncrementCounter">+2</button>
    <button @click="reset">Reset</button>
  </div>
  </div>
</template>

<style scoped>

.container{
  text-align: center;
  border: 2px solid black;
  justify-content: center;
  padding: 20px;
  margin: 20px;
  border-radius: 10px;
}
button{
  width: 120px;
  height: 50px;
  font-size: x-large;
  margin: 20px;
  border-radius: 10px;
}
h1{
  font-size: 60px;
  font-weight: bold;
  background-color: purple;
  height: 80px;
  color: #fff;
}
h2{
  font-size: 60px;
  font-weight: bold;
}
h3{
  font-weight: bold;
}
.odd{
  color: red;
}
.even{
  color: green;
}
</style>
