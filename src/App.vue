<template>
  <div id="app">
    <h1>Vue.js Projects</h1>
    <div class="app1">
      <div class="body-1">
        <bounce-ball></bounce-ball>
      </div>
    </div>
    <div class="app">
      <div class="unit" v-for="(unit, i) in manifest" :key="i">
        <child :item="unit.item" :url="unit.url"></child>
      </div>
    </div>
    <div>
      <div class="location-contain">
        <div class="locations" v-for="(location, i) in locations" :key="i">
          <Place :location="location">
            <h2>{{ location.name }}</h2>
          </Place>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Child from "./components/Child";
import Place from "./components/Place";
import BounceBall from "./components/BounceBall";

export default {
  components: {
    Child,
    Place,
    BounceBall
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
      ],
      locations: [
        {
          name: "moscow",
          img: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/moscow.svg",
          desc: `Moscow is the capital and most populous city of Russia, with 13.2 million residents within the city limits and 17.8 million within the urban area. Moscow has the status of a Russian federal city.`
        },
        {
          name: "paris",
          img: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/paris1.svg",
          desc: `Paris is the capital and most populous city of France. By the 17th century, Paris was one of Europe's major centres of finance, commerce, fashion, science, and the arts, and it retains that position still today.`
        },
        {
          name: "rome",
          img: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/rome.svg",
          desc: `Rome's history spans more than 2,500 years. While Roman mythology dates the founding of Rome at around 753 BC, the site has been inhabited for much longer, making it one of the oldest continuously occupied sites in Europe.`
        },
        {
          name: "paris",
          img: "https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/paris2.svg",
          desc: `Paris is the capital and most populous city of France. By the 17th century, Paris was one of Europe's major centres of finance, commerce, fashion, science, and the arts, and it retains that position still today.`
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
h1 {
  text-align: center;
  font-size: 3rem;
  font-weight: 900;
  font-family: "PT Serif", serif;
}
.app {
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
}
.location-contain {
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: center;
  justify-content: center;
}

.place {
  display: -webkit-box;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  flex-direction: column;
  width: 200px;
  height: 350px;
  -webkit-box-pack: center;
  justify-content: center;
  background: white;
  border: 1px solid #ddd;
  padding: 20px 20px;
  margin: 10px;
}
.place h2 {
  margin: 0;
  text-align: center;
}
.place img {
  margin: 10px;
  align-self: center;
}
/* from here */
.app1 {
  text-align: center;
  margin: 60px;
  max-width: 320px;
  margin: 0 auto;
  display: table;
}
.body-1 {
  font-family: "Bitter", serif;
  width: 100vw;
  height: 100vh;
  background: #eeeeee;
  /* Old browsers */
  /* FF3.6-15 */
  /* Chrome10-25,Safari5.1-6 */
  background: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(#eeeeee),
    color-stop(65%, #cccccc),
    color-stop(99%, #eeeeee)
  );
  background: linear-gradient(to bottom, #eeeeee 0%, #cccccc 65%, #eeeeee 99%);
  /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#eeeeee', endColorstr='#eeeeee',GradientType=0 );
  /* IE6-9 */
}
/* to here */
</style>
