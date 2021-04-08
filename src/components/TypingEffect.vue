<template>
    <div class="typing-wrapper" >
        <p id=prem>{{ $t('home.typingFirst') }}</p>
        <p id=deux>{{ $t('home.typingSecond') }}<span>|</span></p>
    </div>
</template>

<script>

</script>

<style scoped>

#prem{
  /*border: solid red 2px;*/
  font-family: "Courier";
  font-size: 18px;
  margin: 10px 0 0 10px;
  white-space: nowrap;
  overflow: hidden;
  width: 20em;
  animation: type 2s steps(25, end) ; 
}

#deux{
  /*border: solid red 2px;*/
  font-family: "Courier";
  font-size: 18px;
  margin: 10px 0 0 10px;
  white-space: nowrap;
  overflow: hidden;
  width: 20em;
  animation: type2 4s steps(27, start) ; 
}

span{
  animation: blink 1s infinite;
}

@keyframes type{ 
  0%{width: 0;}
  100%{ width: 100; } 
} 

@keyframes type2{
  0%{width: 0;}
  50%{width: 0;}
  100%{ width: 100; } 
} 

@keyframes blink{
  to{opacity: .0;}
}

</style>