<template>
    <div class="panel">
        <p style="text-align:center;">Are you a Modern player who misses a time <strong>before Horizons</strong> set power creep, breakneck release schedules, and Universes Beyond?
        <br>
        <br>Do you yearn to summon a huge <strong>Tarmogoyf</strong>, combo kill with Pod and <strong>Splinter Twin</strong>, or swarm the field with artifact creatures?
        </p>
        <h3 style="text-align:center; background:transparent; color:var(--col-red)">It’s time to reignite your love for Modern.</h3>
        <p style="text-align: center;">Introducing <strong>PreFIRE</strong> - A community-built, open source retro format.</p>

        <div class="panel-button">
            <NavButton  :button>Learn More</NavButton>
        </div>
    </div>
</template>

<script setup>
import NavButton from '../NavButton.vue';
import { ref } from 'vue';

const button = ref({
  name: "Start Playing Now",
  link: "https://discord.gg/P7bV8ttzgT",
  frame: "artifact"
})
</script>

<style scoped>
.panel {
  display: flex;
  flex-direction: column;
}

.panel-button {
  width: 50%;
  margin-inline: 25%;
}
</style>
