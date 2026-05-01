<template>
    <p>To ensure PreFIRE maintains its identity as a nostalgic format, cards and strategies iconic to classic Modern will take priority when making banlist decisions. </p>
    <div id="image-container-pillars">
        <hoverableCard 
            v-for="pillarCard in pillarCardNames" 
            :key="pillarCard"
            :cardName="pillarCard"
        />
    </div>
    <p style="text-align:center">These cornerstone cards will always remain legal, even if the decks they feature in must be weakened to maintain format balance. 
    <br>Bans will always target cards surrounding these pillars — never the pillars themselves.
    <br>This list is by no means exhaustive or fixed and may change as the format develops.
    </p>
</template>

<script setup>
import hoverableCard from "../HoverableCard.vue";

const pillarCardNames = [
    "Splinter Twin",
    "Tarmogoyf",
    "Birthing Pod",
    "Faithless Looting",
    "Mox Opal",
    "Noble Hierarch",
]
</script>

<style scoped>
#image-container-pillars {
    display: flex;
    columns: 6;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2px;
    margin: 5px;
}
#image-container-pillars img {
  flex: 1;
  width: 0;              
  object-fit: cover;
}
</style>
