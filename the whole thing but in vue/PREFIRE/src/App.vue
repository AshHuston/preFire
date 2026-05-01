<template>
  <MainLayout>
    <Panel 
      v-for="(panel, index) in panels"
      :key="index"
      :title="panel.title"
      :image="panel.image"
      :centerTitle="panel.centerTitle"
      :centerText="panel.centerText"
      >
        <component class="panel-content" :is="panel.content" v-if="typeof panel.content === 'object'"></component>
        <p class="panel-content" v-else>{{ panel.content }}</p>
      </Panel>
  </MainLayout>
  
</template>

<script setup>
import MainLayout from './components/mainLayout.vue';
import Panel from './components/Panel.vue';
import StartPlaying from './components/panelContent/StartPlaying.vue';
import AboutPF from './components/panelContent/AboutPF.vue';
import WhatIsPF from './components/panelContent/WhatIsPF.vue';
import Pillars from './components/panelContent/Pillars.vue';
import { onMounted, ref } from 'vue';

const tarmogoyfImage = ref(null);
const panels = ref([]);

onMounted(async () => {
  const res = await fetch("https://api.scryfall.com/cards/named?fuzzy=tarmogoyf");
  const data = await res.json();
  const printRes = await fetch(data.prints_search_uri);
  const printData = await printRes.json();
  const lastPrint = printData.data.at(-2); // Specific print chosen for its art crop image

  tarmogoyfImage.value = lastPrint?.image_uris?.art_crop ?? null;

  panels.value = [
    {
      title: "PreFIRE Modern",
      image: tarmogoyfImage.value,
      centerTitle: true,
      centerText: true,
      content: StartPlaying
    },
    {
      title: "About PreFIRE",
      centerTitle: false,
      centerText: false,
      content: AboutPF
    },
    {
      title: "What is PreFIRE?",
      centerTitle: false,
      centerText: false,
      content: WhatIsPF
    },
    {
      title: "Pillars of PreFIRE",
      centerTitle: false,
      centerText: false,
      content: Pillars
    }
  ]
});

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

:global(p) {
  font-family: Arial, Helvetica, sans-serif;
}

.panel-content {
  padding: 0px 15px;
}

</style>
