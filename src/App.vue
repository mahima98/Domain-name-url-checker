<template>
  <div id="app">
    <div class="container mx-auto bg-red-200">
      <div class="flex flex-col justify-center items-center h-screen">
        <div class="bg-blue-300 p-10 flex flex-col gap-4 rounded-lg">
          <div>
            <div class="text-lg font-extrabold">Main url: </div>
            <input type="text" class="p-2">
          </div>
          <div>
            <div class="text-lg font-extrabold">Custom url: </div>
            <input v-model="nameInput" type="text" class="p-2">
          </div>
          <button class="bg-black text-white p-2">Check</button>
          <div class="errorOutput"></div>
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
      
    }
  },

  methods: {
  }
}
</script>
