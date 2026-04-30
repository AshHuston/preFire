<template>
  <MainLayout>
    <Panel title="DDDD" :image="tarmogoyfImage">Test1</Panel>
    <Panel >Test2</Panel>
    <Panel>Test3wdhvbwudhvwbwqugdvowubv ouwebvou  wegfkvcw  bcuhj wnvbcwuyqjhvgbwoyiuvhgbweoidyuvgb<br /><br /><br /><br /><br />qwioyukvjgbwroiydhkfgvbwlisydkhfgbwoeisydkhgfbvwilsydhfgbvlsiydkhfgbvlsiykdjfghsliudkjfhvslnz</Panel>
  </MainLayout>
  
</template>

<script setup>
import MainLayout from './components/mainLayout.vue';
import Panel from './components/Panel.vue';
import tarmogoyfImage from './RESOURCES/img/backgrounds/tarmogoyf.webp';

</script>

<style scoped>

@font-face {
  font-family: "Beleren";
  src: url("./RESOURCES/font/Beleren.ttf") format("truetype");
}

:global(:root) {

  --nav-items: 5;
  --nav-item-width: calc(90% / var(--nav-items));

  --col-white: #fbfcc2; --col-ui-white: #f3f2ef;
  --col-blue : #7ebff0; --col-ui-blue : #c6d8e6;
  --col-black: #848484; --col-ui-black: #c4bdbc;
  --col-red  : #e75f5f; --col-ui-red  : #f4cab5;
  --col-green: #53b16b; --col-ui-green: #bfccc2;
  --col-ui-artifact: #dfdfe3;



  --col-regular : var(--col-white);
  --col-lightest: color-mix(in srgb, var(--col-regular) 40%, white);
  --col-lighter : color-mix(in srgb, var(--col-regular) 60%, white);
  --col-darker  : color-mix(in srgb, var(--col-regular) 60%, black);
  --col-darkest : color-mix(in srgb, var(--col-regular) 40%, black);

  --col-dark-1: #111;
  --col-dark-2: #222;

  --col-dark-1-transparent: rgba(17, 17, 17, 1);
  --col-dark-2-transparent: rgba(34, 34, 34, 0.93);
}

</style>
