<template>
  <div id="app">
    <div class="container mx-auto bg-red-200">
      <div class="flex flex-col justify-center items-center h-screen">
        <div class="bg-blue-300 p-10 flex flex-col gap-4 rounded-lg">
          <div>
            <div class="text-lg font-extrabold">Main url: </div>
            <input type="text" v-model="mainUrl" class="p-2 text-gray-400">
          </div>
          <div>
            <div class="text-lg font-extrabold">Custom url: </div>
            <input v-model="customUrl" type="text" class="p-2">
          </div>
          <button class="bg-black text-white p-2" v-on:click="onDisplayInputUrl()">Display Input URL</button>
          <div class="errorOutput">{{this.outputCustomUrl}}</div>
          <div class="output"></div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      mainUrl: 'http://mahima.ramgolam.com',
      outputCustomUrl: null,

    }
  },

  methods: {
    onDisplayInputUrl() {
      this.outputCustomUrl = this.customUrl
    }
  }
}
</script>
