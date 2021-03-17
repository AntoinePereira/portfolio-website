<template>
  <div id='preferences'>
    <h1>{{ mode }} Mode</h1>
    <Toggle :mode="mode" @toggle="$emit('toggle')" />
  </div>
</template>

<script>
import Toggle from '@/components/Toggle'
export default {
  props: ['mode'],
  components: {
    Toggle
  }
}
</script>

<style>
#preferences {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 25px;
  height: 60px;
  transition: background 0.3s ease-in-out;
}

#preferences h1 {
  font-size: 32px;
  text-transform: uppercase;
  font-weight: 900;
}

</style>