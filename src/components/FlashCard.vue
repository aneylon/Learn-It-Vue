<script>
export default {
  data() {
    return {
      showCardBack: false,
      currentCardIndex: 0,
      currentCard: {
        question: "This is a question",
        answer: "This is an answer",
        explanation: "This is an explanation",
      },
      cards: [
        { question: "One", answer: "One", explanation: "One" },
        { question: "Two", answer: "Two", explanation: "Two" },
        { question: "Three", answer: "Three", explanation: "Three" },
        { question: "Four", answer: "Four", explanation: "Four" },
      ],
    };
  },
  methods: {
    toggleCardBack() {
      this.showCardBack = !this.showCardBack;
    },
    nextCard() {
      console.log("Go to the next card");
      this.currentCardIndex += 1;
    },
    shuffleCards() {
      console.log("shuffle cards");
    },
    cardResponse(response) {
      console.log(response, "this card");
      // todo : save user response
      // push card to relevant array
      // decide what to do next
      console.log(this.currentCardIndex, this.cards.length);
      if (this.currentCardIndex === this.cards.length) {
        this.shuffleCards();
      } else {
        this.nextCard();
      }
    },
  },
};
</script>

<template>
  <div>
    <div @click="toggleCardBack">{{ currentCard.question }}</div>
    <div id="cardBack" v-show="showCardBack">
      <div>{{ currentCard.answer }}</div>
      <div>{{ currentCard.explanation }}</div>
    </div>
    <div id="buttons">
      <button @click="cardResponse('Know')">Know</button>
      <button @click="cardResponse('NotSure')">Not sure</button>
      <button @click="cardResponse('DontKnow')">Don't Know</button>
    </div>
  </div>
</template>
