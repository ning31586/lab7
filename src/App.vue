<template>
  <div id="app">
    <br />
    <b-avatar
      src="https://upload.wikimedia.org/wikipedia/th/4/43/%E0%B8%A1%E0%B8%AB%E0%B8%B2%E0%B8%A7%E0%B8%B4%E0%B8%97%E0%B8%A2%E0%B8%B2%E0%B8%A5%E0%B8%B1%E0%B8%A2%E0%B9%81%E0%B8%A1%E0%B9%88%E0%B9%82%E0%B8%88%E0%B9%89_edit.png"
      size="15%"
    ></b-avatar>
    <HelloWorld id="text" msg="Comsci 352" />
    <music />
    <footer class="my-0 pt-0 text-muted text-center text-small">
        <p class="mb-0">&copy; cs313 &copy; 6104101352</p>
    </footer>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import music from "./components/music.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    music,
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-size: cover;
  background-image: url();
}
#text {
  color: rgb(0, 0, 0);
}
</style>
