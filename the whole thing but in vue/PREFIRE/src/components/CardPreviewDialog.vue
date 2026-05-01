This is unused for now but I want to keep it around as a reference for how to do this in the future. I know it can be done, I just don't have the time to debug it right now.

<template>
     <img :src="imageUrl" :alt="cardName" class="card" />
</template>

<script setup>
defineProps({
    cardName: String,
    imageUrl: String
})
</script>

<style scoped>
img {
    position: absolute;
    pointer-events: none;
    top: 0;
    left: 0;
    z-index: 999;
    width  : 100vw; height: 100vh;
    display: none ; align-items: center; justify-content: center;
    background-color: transparent;
    overflow        : hidden;
    perspective     : 800px;
    &:focus-visible{outline:none;border:none}
    &::backdrop    {background-image: radial-gradient(black,transparent);}

    width:auto; height: 80%;
    padding       : 0px;
    border-radius : 30px;
    will-change:transform; transform-style:preserve-3d; 
    backface-visibility :hidden; 
    transition          :transform 120ms ease; 
    display             :block;
    &:hover{transform:none;}
}
</style>
