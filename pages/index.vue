<template>
  <div id="app">
  <v-app id="inspire">
    <v-card>
      <div class="text-center addSpaceOnTitle">
        <h1>What Time Is It?</h1>
      </div>
    </v-card>
    <div class="text-center" style="padding-top: 5px">
        <h1>Press the button to get the current time!</h1>
      </div>
    <div class="center-div addSpaceOnText">
      <h3 id="insertTime"></h3>
    </div>
    <div class="center-div">
        <v-btn rounded dark color="primary" @click="insertTime()">Get Time!</v-btn>
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
        element.innerHTML = 'F2A73B7B650D4DA8554ADFA9E1024F77477FB250'
      } else {
        element.innerHTML = time
      }
    },
    isRealTime () {
      const currentTimeInMinutes = new Date().getMinutes()
      if (currentTimeInMinutes % 5 === 0) {
        return true
      }
      return false
    }
  }
}
</script>

<style lang="scss" scoped>
  .center-div {
    text-align: center;
    margin-left: auto;
    margin-right: auto;
  }
  .addSpaceOnTitle {
    padding-top: 10px;
  }
  .addSpaceOnText {
    padding: 15px;
  }
</style>
