<script>
let id = 0;

export default {
  data() {
    return {
      word: "",
      words: [],
    };
  },
  methods: {
    addword() {
      this.words.push({ id: id++, text: this.newWord });
      this.newWord = "";
    },
  },
};
</script>

<template>
  <div>
    <form @submit.prevent="addword">
      <input v-model="newWord" />
      <button>Guess Word</button>
    </form>
    <ul>
      <li v-for="word in words" :key="word.id">
        {{ word.text }}
      </li>
    </ul>
  </div>
</template>