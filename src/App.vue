<template>
  <div id="app">
    <div id="ranking">
      <div id="brand">
        <router-link to="/">
          <img src="/images/logo.png">
        </router-link>
      </div>
      <div id="side">
        <router-link to="/browse">
          <div class="athletes browse">
            <img src="/images/browse.png">
            <p>Browse</p>
          </div> 
        </router-link>
        <router-link to="/compare">
          <div class="ranking-item">
            <img src="/images/love.png">
            <p> {{iNum}} Athletes</p>
          </div>
        </router-link>
      </div>
    </div>
    <router-view/>
    <div class="footer-container">
      <div class="footer">
        <a href="https://github.com/bunnycustard/cp3"><img src="/images/github.png"></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
    }
  },
  computed: {
    iNum() {
      return this.$root.$data.compare.length;
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 50px 100px;
}
#ranking {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}
#ranking a {
  color: #000000;
}
#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}
#brand img {
  height: 200px;
}
#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}
#side img {
  width: 50px;
}
.ranking-item {
  display: flex;
  flex-direction: column;
}
.ranking-item p {
  margin: 0px;
}
.browse {
  margin-right: 50px;
}
</style>
