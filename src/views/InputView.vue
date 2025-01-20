<script setup>
import 'bulma/css/bulma.css'
import '@/assets/main.css'
</script>

<template>
  <div class="textareaP has-background-white p-4 is-rounded">
    <div
      contenteditable="true"
      @input="handleInput"
      :data-placeholder="placeholderText"
      style="width: 100%; padding: 8px; box-sizing: border-box; min-height: 50px; outline: none"
    ></div>
    <p style="margin-top: 8px; font-size: 14px; color: #959292">
      {{ characterCount }}/{{ maxCharacters }} characters
    </p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      characterCount: 0,
      maxCharacters: 10000,
      placeholderText: 'Type something...',
      questionText: 'What is your name?',
      responseText: 'My name is GitHub Copilot.',
    }
  },
  methods: {
    handleInput(event) {
      const text = event.target.innerText.trim() // Trim to remove empty spaces and newlines
      this.characterCount = Math.min(text.length, this.maxCharacters) // Update character count
      if (text.length > this.maxCharacters) {
        event.target.innerText = text.slice(0, this.maxCharacters) // Truncate if over max
        const range = document.createRange()
        const sel = window.getSelection()
        range.selectNodeContents(event.target)
        range.collapse(false)
        sel.removeAllRanges()
        sel.addRange(range)
      }
    },
  },
}
</script>
<style scoped>
.textareaP {
  max-width: 520px;
  width: 100%;
  border-radius: 15px;
  margin-bottom: 20px;
  font-size: 14px;
}
</style>
