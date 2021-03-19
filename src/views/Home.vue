<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TypingEffect v-if="lang === english"/>
  </div>
</template>

<script>
// @ is an alias to /src
import TypingEffect from '../components/TypingEffect.vue'
export default {
  name: 'Home',
  props: ['lang'],
  components: {
    TypingEffect
  }
}
</script>
