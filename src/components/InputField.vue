<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'InputField',
  props: {
    inputText: String,
  },
  data() {
    return {
      inputValue: this.inputText || '',
      interval: 0,
      progression: 0,
      value: ''
    }
  },
  methods: {
    checkInput() {
      this.progression = ( this.value.length / this.inputValue.length)*100
    },
  },
  // computed: {
  //   progress() {
  //     return Math.min(100, this.inputText.length * 10)
  //   },
  //   color() {
  //     return ['error', 'warning', 'success'][Math.floor(this.progress / 40)]
  //   },
  // },
})
</script>

<template>
  <v-container
    class="green lighten-2"
    fluid
  >
    <v-row>
      <v-col cols="4">
        <div
          class="ma-auto"
          style="max-width: 300px"
        >
          <v-input>{{ inputValue }}</v-input>
        </div>
      </v-col>
      <v-col cols="4">
        <div
          class="ma-auto"
          style="max-width: 300px"
        >
          <v-text-field
            v-model="value"
            color="cyan darken"
            label="Text field"
            placeholder="Start typing..."
            loading
            @input="checkInput"
          >
          </v-text-field>
        </div>
      </v-col>
      <v-col
        cols="2"
        class="my-3"
      >
        <v-progress-linear
          v-model="progression"
          color="black"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<style>
.center {
  display: flex;
  place-content: center;
}
</style>
