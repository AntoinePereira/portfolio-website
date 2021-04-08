<template>
  <div id="app" :class="mode">
    <div id="nav">
      <div class="leftBtn">
        <router-link :to="`/${$i18n.locale}`">Home </router-link>
      </div>
      <div class="rightBtn">
        <router-link :to="`/${$i18n.locale}/projects`">Projects</router-link>
      </div>
    </div>
    <Preferences id='preferences' :mode="mode" @toggle="toggle" :lang="lang" @toggleLang="toggleLang" />
    <router-view/>
  </div>
</template>


<script>
import Preferences from '@/components/Preferences'
export default {
  name: 'app',
  data () {
    return {
      mode: localStorage.getItem('mode') || 'dark',
      lang: localStorage.getItem('lang') || 'english'
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
      localStorage.setItem('mode', this.mode)
    },
    toggleLang () {
      if (this.lang === "french") {
        this.lang = "english"
        this.setLocale('en')
      } else {
        this.lang = "french"
        this.setLocale('fr')
      }
      localStorage.setItem('lang', this.lang)
    },
    setLocale(locale) {
      this.$i18n.locale = locale
      this.$router.push({
        params: { lang: locale }
      })
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
  background: #022c43;
  color: #E8E8E8;
  transition: background 0.3s ease-in-out;
  #nav{
    border-bottom: solid #ffd700 1px;
    a{
      color: #ffd700;
    }
  }
  #preferences{
    background-color: #115173;
    border-bottom: solid #ffd700 1px;
  }
}
.light{
  background: #F3F3F3;
  color: #022c43;
  transition: background 0.3s ease-in-out;
  #nav{
    border-bottom: solid #022c43 2px;
    a{
      color: #022c43;
    }
  }
  #preferences{
    border-bottom: solid #022c43 2px;
  }
}

#nav {
  display: flex;
  justify-content: space-around;
  .leftBtn{
    display: flex;
    justify-content: center;
    padding: 25px;
    width: 50vw;
    background-image: linear-gradient(to bottom right, #022c43, #053f5e, #115173);
  }
  .rightBtn{
    display: flex;
    justify-content: center;
    padding: 25px;
    width: 50vw;
    background-image: linear-gradient(to bottom right, #022c43, #053f5e, #115173);
  }
  a {
    font-weight: bold;
    &.router-link-exact-active {
      text-decoration:underline;
    }
  }
}

</style>
