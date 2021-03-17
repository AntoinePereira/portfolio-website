<template>
  <div id="app" :class="mode">
    <div id="nav">
      <router-link to="/">Home </router-link>
      <router-link to="/Projects">Projects</router-link>
    </div>
    <Preferences :mode="mode" @toggle="toggle" />
    <router-view/>
  </div>
</template>


<script>
import Preferences from '@/components/Preferences'
export default {
  name: 'app',
  data () {
    return {
      mode: 'light'
    }
  },
  components: {
    Preferences
  },
  methods: {
    toggle () {
      if (this.mode === "dark") {
        this.mode = "light"
      } else {
        this.mode = "dark"
      }
    }
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  width: 100vw;
  min-height: 100vh;
  
}

.dark {
  background: #192734;
  color: #E8E8E8;
  transition: background 0.3s ease-in-out;
  #nav{
    border-bottom: solid white 2px;
  }
}
.light{
  background: #F3F3F3;
  color: #15202B;
  transition: background 0.3s ease-in-out;
}

#nav {
  padding: 30px;
  border-bottom: solid black 2px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

</style>
