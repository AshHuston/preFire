<template>
    <a :href="button.link" >
        <button :class="button.frame">
            <img 
                v-if="button.frame === 'nav-home'"
                class="icon"
            />
            {{ button.name }}
        </button>
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

.icon {
  width: 100px;
  height: 100px;
  background-color: rgb(191, 189, 189); /* your desired color */

  -webkit-mask-image: url("../RESOURCES/img/ui/home.png");
  -webkit-mask-repeat: no-repeat;
  -webkit-mask-size: contain;

  mask-image: url("../RESOURCES/img/ui/home.png");
  mask-repeat: no-repeat;
  mask-size: contain;

  &:hover{
    background-color       : black;
    z-index     : 2;
    transition  : 0.2s;
    cursor      : pointer;
  }
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
a.nav-home img   { width: 2em; height: 2em; }
a, button {
  --border-natural-size: 48px;
  --border-half-size   : 24px;
  flex: 1;
  width: 90%;
  margin-top: -20px;

  border              : var(--border-half-size) solid transparent;
  border-image        : url(border.png) 33 round;
  border-radius       : var(--border-natural-size); 

  text-decoration     : none;
  font-family         : Beleren;
  font-size           : 1.15em;
  color               : black;

  justify-content: center;
  align-items: center;

  z-index     : 1;
  transition  : 0.2s;
  filter      : saturate(0.8) contrast(0.8) drop-shadow(0px 3px 3px black);
  --height    : 20px;
  height      : --height;
  line-height : --height;
  &:hover{
    filter      : saturate(1.0) contrast(1.2) drop-shadow(0px 3px 9px black);
    text-shadow : 0px 3px 10px #222222ee;;
    color       : #111;
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
  height: 70px;
  line-height: 1em;
}
.nav-home {
  background-color    : transparent;
  transform          : translateY(-15%);
  filter      : drop-shadow(0px 0px 0px black);
  &:hover{
    filter      : saturate(1.0) contrast(1.2) drop-shadow(0px 0px 0px black);
    text-shadow : 0px 3px 10px #222222ee;
    color       : #111;
    z-index     : 2;
    transition  : 0.2s;
    cursor      : pointer;
  }
}


</style>
