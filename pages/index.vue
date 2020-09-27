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
      if (this.isRealTime() === 1) {
        element.innerHTML = 'test'
      } else if (this.isRealTime() === 2) {
        element.innerHTML = 'F2A73B7B650D4DA8554ADFA9E1024F77477FB250'
      } else {
        element.innerHTML = time
      }
    },
    isRealTime () {
      const currentTimeInMinutes = new Date().getMinutes()
      if (currentTimeInMinutes % 3 === 0) {
        return 1
      }
      if (currentTimeInMinutes % 9 === 0) {
        return 2
      }
      return 0
    }
  }
}
</script>
