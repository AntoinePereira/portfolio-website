<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TypingEffect/>
  </div>
</template>

<script>
// @ is an alias to /src
import TypingEffect from '../components/TypingEffect.vue'
export default {
  name: 'Home',
  components: {
    TypingEffect
  }
}
</script>
