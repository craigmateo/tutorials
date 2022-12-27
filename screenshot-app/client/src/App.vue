<template>
  <div id="app">
    <header>
      <h1>Take a screenshot</h1>
    </header>
    <main>
      <form @submit.prevent="requestScreenshot">
        <input type="url" name="url" id="url" v-model="url" />
        <input type="submit" value="Take screenshot">
      </form>
      <a v-if="screenshotUrl != ''" :href="screenshotUrl" target="_blank" download>
        <img :src="screenshotUrl" />
      </a>
    </main>
  </div>
</template>

<script>

import { ref } from 'vue';

export default {
  name: 'App',
  setup() {
    const url = ref("http://");
    const screenshotUrl = ref("");

    const requestScreenshot = async () => {

      console.log(url.value);
/*       const res = await fetch('http://localhost:5000/screenshot', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({
          url: url.value
        })
      }).then(data => data.json)

      console.log(res); */

    }

    return {
      url,
      screenshotUrl,
      requestScreenshot
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
