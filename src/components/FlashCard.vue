<script setup>
import { ref } from "vue";
let showCardBack = ref(true);

const toggleCardBack = () => {
  console.log("toggle");
  showCardBack = !showCardBack;
  console.log(showCardBack);
};

function knowCard() {
  console.log("Know Card");
}
function dontKnowCard() {
  console.log("Dont Know Card");
}
function notSureCard() {
  console.log("Not Sure Card");
}
</script>

<template>
  <div>
    <div @click="toggleCardBack">question</div>
    <div id="cardBack" v-show="showCardBack">
      <div>answer</div>
      <div>explain</div>
    </div>
    <div id="buttons">
      <button @click="knowCard">Know</button>
      <button @click="notSureCard">Not sure</button>
      <button @click="dontKnowCard">Don't Know</button>
    </div>
  </div>
</template>
