<template>
  <div id="app">
  <v-app id="inspire">
    <div class="text-center">
      <h1>What Time Is It?</h1>
      <h3 id="insertTime"></h3>
      <v-btn rounded dark color="primary" @click="insertTime()">Get Time</v-btn>
    </div>
  </v-app>
</div>
</template>

<script>
export default {
  methods: {
    currentTime () {
      let currentTime = new Date()
      currentTime = currentTime.toUTCString()
      return currentTime
    },
    insertTime () {
      const time = this.currentTime()
      const element = document.getElementById('insertTime')
      if (this.isRealTime()) {
        element.innerHTML = 'test'
      } else {
        element.innerHTML = time
      }
    },
    isRealTime () {
      const currentTimeInMinutes = new Date().getMinutes()
      if (currentTimeInMinutes % 3 === 0) {
        return true
      }
      return false
    }
  }
}
</script>
