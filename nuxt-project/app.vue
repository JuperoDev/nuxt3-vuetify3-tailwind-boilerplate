<template>
  <div>
    {{ message }}
    {{ count }}
    <button @click="decreaseCount">-</button>
    <button @click="increaseCount">+</button>
{{ multiplicado }}
{{ newText }}

<br/>



<br/>
<br/>
<br/>

<br/>
{{ whatever.$state.contador }}
<button @click="whatever.incrementar">+</button>

<button @click="whatever.decrementar">-</button>
  </div>
</template>

<script setup>

import { ref } from "vue";
import { useCounterStore } from "./stores/counter";

const whatever = useCounterStore ();


const message = ref("holada");
const count = ref(0);
const newText = ref ('');

const increaseCount = () => {
  count.value++;
};

const decreaseCount = () => {
  count.value--;
};

const multiplicado = computed ( () => {
  return count.value*2
}
)

watch (multiplicado, (newValue, oldValue) => {
  return newText.value = `multiplicado changed from ${oldValue } to ${newValue}`
  
})
</script>
