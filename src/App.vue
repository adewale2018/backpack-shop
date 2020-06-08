<template>
  <div id="app">
    <div class="unit" v-for="(unit, i) in manifest" :key='i'>
    <child :item="unit.item" :url="unit.url"></child>
  </div>
  </div>
</template>

<script>
import Child from "./components/Child";

export default {
  components: {
    Child
  },
  name: "app",
  data() {
    return {
      counter: 0,
      manifest: [
        {
          item: "backpack",
          url: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/backpack.jpg"
        },
        {
          item: "tshirt",
          url: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/tshirt.jpg"
        },
        {
          item: "sweatshirt",
          url:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/sweatshirt.jpg"
        }
      ]
    };
  }
};
</script>

<style>
body,
html {
  font-family: "PT Serif", serif;
}
#app {
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
}

</style>
