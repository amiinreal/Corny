<script setup>
import 'bulma/css/bulma.css'
import '@/assets/main.css'
import InputView from './views/InputView.vue'
</script>

<template>
  <div class="boss">
    <img alt="Vue logo" class="logo" src="@/assets/logo.png" width="50" height="50" />
    <div class="chat-container">
      <div class="chat-message question">
        <p>{{ questionText }}</p>
      </div>
      <div class="chat-message response">
        <p>{{ responseText }}</p>
      </div>
    </div>
    <div class="input-view-container">
      <InputView />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questionText: 'What is your name?',
      responseText:
        'Selvfølgelig! Her er noen eksempler på instruksjoner du kan bruke:  \r 1 Matlaging: Kan du gi meg en oppskrift på en enkel pastarett? \n 2. Reise: Hva er de beste turistattraksjonene i Paris?',
    }
  },
}
</script>

<style scoped>
.boss {
  background-color: #f0f0f0;
  width: 100%;
  height: 100vh;

  display: flex;
  flex-direction: column;
  align-items: center;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

.chat-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  flex-grow: 1;
  width: 100%;
  max-width: 100%;
  overflow-y: auto;
}

.chat-message {
  padding: 1rem;
  border-radius: 8px;
  max-width: 60%;
}

.question {
  margin-right: 100px;
  max-width: 620px;
  background-color: #3f9cf5;
  color: white;
  align-self: flex-end;
  float: right;
}

.response {
  margin-left: 100px;
  max-width: 620px;
  background-color: white;
  color: black;
  align-self: flex-start;
  border: 1px solid #ccc;
  float: left;
}

.input-view-container {
  width: 100%;
  max-width: 600px;
  background-color: white;
  border-radius: 15px;
  margin-bottom: 30px;
}
</style>
