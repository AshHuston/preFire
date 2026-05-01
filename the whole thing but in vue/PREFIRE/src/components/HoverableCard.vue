<template>
        <img
            :src="imageUrl"
            :alt="cardName"
            class="hoverable-card"
            @click="displayPreview = true"
        />


        <!-- This was not working as expected but I did not want to devote a nunch of time to debugging. I know it COULD work just fine. -->
         
        <!-- <CardPreviewDialog
            v-if="displayPreview"
            :cardName="cardName"
            :imageUrl="imageUrl"
        /> -->
</template>

<script setup>
import { onMounted, computed, ref } from 'vue';
import CardPreviewDialog from './CardPreviewDialog.vue';

const props = defineProps({
    cardName: String,
})

const displayPreview = ref(false);

const requestUrl = computed(() => {
    return `https://api.scryfall.com/cards/named?fuzzy=${props.cardName}`;
});

const imageUrl = ref('');

onMounted(async () => {
  try {
    const cardData = await fetch(requestUrl.value).then(r => r.json());
    const printData = await fetch(cardData.prints_search_uri).then(r => r.json());

    const lastPrint = printData.data.at(-1);

    imageUrl.value =
      lastPrint?.image_uris?.normal ??
      lastPrint?.card_faces?.[0]?.image_uris?.normal ??
      null;

  } catch (err) {
    console.error(err);
  }
});
</script>

<style scoped>

@keyframes cardEffectIn{
    0%{transform:rotateX(  0deg) }
   10%{transform:rotateX(-10deg) rotateY(-10deg)               scale(1.1); }
  100%{transform:rotateX(  5deg) rotateY(  5deg) rotateZ(2deg) scale(1.2); }
}
@keyframes cardEffectOut{
    0%{transform:rotateX(  5deg) rotateY(  5deg) rotateZ(2deg) scale(1.2); }
   10%{transform:rotateX(-10deg) rotateY(-10deg)               scale(1.1); }
  100%{transform:rotateX(  0deg) }
}

.hoverable-card {
    background-size: cover;
    background-position: center;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
    border-radius: 5%;
    height: auto;
    width: auto;
    position: relative;

    animation : cardEffectOut  0.5s forwards ease;
    z-index   : 1; 
}

.hoverable-card:hover {
    animation : cardEffectIn 0.2s forwards ease;
    z-index   :2;
    cursor    :pointer;
}
</style>
