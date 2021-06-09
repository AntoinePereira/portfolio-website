<template>
  <div class="home">
    <TypingEffect class="typingEffect" :class="mode"/>
    <div class="tablette">
    <img class='wam' alt="Vue logo" src="../assets/photowidth300px.png"/>
    <div class="about">
      <h1>{{ $t('home.aboutMe.title') }}</h1>
      <p>{{ $t('home.aboutMe.text') }}</p>
    </div>
    </div>
    <div class="links">
      <a href="https://github.com/AntoinePereira"><img src='@/assets/github.svg'></a>
      <a href="https://www.linkedin.com/in/antoine-pereira-b9a828201/"><img src='@/assets/linkedin.svg'></a>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TypingEffect from '../components/TypingEffect.vue'
export default {
  name: 'Home',
  data () {
    return {
      mode: localStorage.getItem('mode') || 'light'
    }
  },
  components: {
    TypingEffect
  }
}
</script>

<style lang="scss" scoped>
.home{
  /*background: #000;*/
  padding-top: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.typingEffect{
  margin-top: 8em;
  margin-bottom: 8em;
}
.tablette{
  display: flex;
  flex-direction: column;
}
.wam{
  border: solid 5px #053f5e;
  border-radius: 10%;
  padding: 0;
  width: 300px;
  align-self: center;
  justify-self: center;
  background-image: linear-gradient(to bottom right, lightgray, #053f5e, lightgray);
}
.about{
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #115173;
  border-bottom:#ffd700 solid 2px;
  margin-top: 2em;
  padding: 1.5em;
  padding-top: 0;
  padding-bottom: 2.5em;
  h1{
    text-decoration: underline;
    padding-bottom: 1em;
    padding-top: 0.5em;

  }
}
.links{
  display: flex;
  justify-content: space-around;
  background-color: #ffd700;
  padding: 2em;
  width: 100vw;
  border: solid 10px#053f5e;
  img{
    width: 50px;
  }
}
.dark{
  .typingEffect{
    background: #022c43;
    color: #ffd700;
  }
}
.light{
  .typingEffect{
    background: #F3F3F3;
    color: #022c43;
  }
}

@media (min-width: 768px){
.tablette{
  display: flex;
  flex-direction: row-reverse;
  background-color: #115173;
  padding: 1em;
}

}
@media (min-width: 991px){

}
</style>
