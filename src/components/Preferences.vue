<template>
  <div id='preferences'>
    <!--<h1>{{ mode }} Mode</h1>
    <Toggle :mode="mode" @toggle="$emit('toggle')" />
    <h1> {{lang}}</h1>-->
    <img src="@/assets/france.svg">
    <LangToggle :lang="lang" @toggleLang="$emit('toggleLang')"/>
    <img src="@/assets/united-kingdom.svg">
  </div>
</template>

<script>
//import Toggle from '@/components/Toggle'
import LangToggle from '@/components/LangToggle'

export default {
  props: ['mode','lang'],
  components: {
    //Toggle,
    LangToggle
  }
}
</script>

<style >
#preferences {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 0px 25px;
  height: 40
  px;
  transition: background 0.3s ease-in-out;
}

#preferences h1 {
  font-size: 16px;
  font-family: "Courier";
  text-transform: uppercase;
  font-weight: 900;
  margin-right: 60px;
}
img{
  width: 30px;
  margin-left: 10px;
  margin-right: 10px;

}

</style>