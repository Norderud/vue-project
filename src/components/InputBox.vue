<script lang="ts">
export default {
  data() {
    return {
      text: '',
    }
  },
}
</script>

<template>
  <div>
    <b-form-textarea
      id="textarea"
      v-model="text"
      placeholder="Enter something..."
      rows="3"
      max-rows="6"
    />

    <pre class="mt-3 mb-0">{{ text }}</pre>
  </div>
</template>
