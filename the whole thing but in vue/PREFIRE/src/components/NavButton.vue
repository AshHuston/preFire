<template>
    <a :href="button.link" >
        <button :class="button.frame">{{ button.name }}</button>
    </a>
</template>

<script setup>
defineProps({
  button: {
    name: String,
    link: String,
    frame: String
  }
})
</script>

<style scoped>
:root {
  --col-white: #fbfcc2; --col-ui-white: 
  --col-blue : #7ebff0; --col-ui-blue : 
  --col-black: #848484; --col-ui-black: 
  --col-red  : #e75f5f; --col-ui-red  : 
  --col-green: #53b16b; --col-ui-green: 
  --col-ui-artifact: ;
}

a.nav-home {
  border       : none !important;
  border-image : none !important;
  background   : none !important;
  width        : 100% !important;
  margin       : 0    !important;
  display      : flex;
  align-items  : center;
  justify-content: center;
  color        : white;
  opacity      : 0.7;
  transition   : opacity 0.2s;
  filter       : none !important;
}
a.nav-home:hover { opacity: 1; cursor: pointer; }
a.nav-home svg   { width: 2em; height: 2em; }
a, button {
  --border-natural-size: 48px;
  --border-half-size   : 24px;
  display: inline-block;
  width: calc(80% - var(--border-natural-size)); margin-inline: 10%;
  
  border              : var(--border-half-size) solid transparent;
  border-image        : url(border.png) 33 round;
  border-radius       : var(--border-natural-size); 

  text-decoration     : none;
  font-family         : Beleren;
  font-size           : 1.5em;
  text-align          : center;
  text-decoration     : none;
  color               : black;

  z-index     : 1;
  transition  : 0.2s;
  filter      : saturate(0.8) contrast(0.8) drop-shadow(0px 3px 3px black);
  --height    : 20px;
  height      : --height;
  line-height : --height;
  &:hover{
    filter      : saturate(1.0) contrast(1.2) drop-shadow(0px 3px 9px black);
    text-shadow : 0px 3px 10px var(--col-dark-2-transparent);
    color       : var(--col-dark-1);
    z-index     : 2;
    transition  : 0.2s;
    cursor      : pointer;
  }
}
.artifact {border-image-source : url("../RESOURCES/img/ui/artifact.webp" );background-color: var(#dfdfe3 );}
.white       {border-image-source : url("../RESOURCES/img/ui/white.webp"    );background-color: var(  #f3f2ef  );}
.blue            {border-image-source : url("../RESOURCES/img/ui/blue.webp"     );background-color: var(  #c6d8e6   );}
.black  {border-image-source : url("../RESOURCES/img/ui/black.webp"    );background-color: var( #c4bdbc  );}
.red             {border-image-source : url("../RESOURCES/img/ui/red.webp"      );background-color: var(  #f4cab5  );}
.green           {border-image-source : url("../RESOURCES/img/ui/green.webp"    );background-color: var(#bfccc2   );}
button {
  margin-block: 15px;
  height: 70px;
  line-height: 1em;
}
</style>
