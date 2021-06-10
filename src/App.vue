<template>
  <div id="app">
    <div class="container mx-auto bg-red-200">
      <div class="flex flex-col justify-center items-center h-screen">
        <div class="bg-blue-300 p-10 flex flex-col gap-4 rounded-lg">
          <div>
            <div class="text-lg font-extrabold">Main url: </div>
            <input type="text" v-model="mainDomainURL" class="p-2 text-gray-400">
          </div>
          <div>
            <div class="text-lg font-extrabold">Custom url: </div>
            <input v-model="customUrl" type="text" class="p-2">
          </div>
          <button class="bg-black text-white p-2" v-on:click="onDisplayInputUrl()">Display Input URL</button>
          <div class="errorOutput text-red-500">{{this.outputResult}}</div>
          <div class="output text-green-700">New Domain name: {{this.customInputURL}}</div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      mainDomainURL: 'http://mahima.ramgolam.com',
      customInputURL: null,
      outputResult: null,
      mainUrl: null,
      customUrl: null,
    }
  },

  methods: {
    onDisplayInputUrl() {
      this.customInputURL = this.customUrl

      this.get_domain_from_url(this.mainDomainURL)
      this.mainUrl = this.domainUrl;
      console.log('mainUrl', this.mainUrl)

      this.get_domain_from_url(this.customInputURL)
      this.customUrl = this.domainUrl;

      if( this.mainUrl == this.customUrl) {
          this.outputResult = "Two Domain have the same name"
      }else {
         this.outputResult = "New domain name is okay!"
      }
    },

    get_domain_from_url(url) {
    if (!url.startsWith('http://') && !url.startsWith('https://')) {
      url = 'http://' + url;
    }
   
    const a = document.createElement('a');
    a.setAttribute('href', url);
    const urlHostName = a.host;
    
    if (urlHostName.indexOf('www.') === 0) {
      this.domainUrl = urlHostName.replace('www.', '');
    } else {
      this.domainUrl = urlHostName;
    }
  
  }
  }
}
</script>
