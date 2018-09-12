<template>
  <div class="training">
  <h1>Math Training Tool</h1>  
  <hr>

<app-start-screen 
v-if="state == 'start'"
@onStart="onStart"
></app-start-screen>

<app-question v-else-if="state == 'question'"></app-question>

<app-message v-else-if="state == 'message'"></app-message>

<app-result-screen v-else-if="state == 'results'"></app-result-screen>

<div v-else>Unknown state</div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      state: 'start'
    }
  },
  methods: {
    onStart() {
      this.state = 'question';
    }
  }
}
</script>

<style scoped>
.training {
  font-family: monospace;
  max-width: 700px;
  margin: 20px auto;
}
</style>
