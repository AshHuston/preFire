<template>
    <div class="gradient-box">
        <button v-for="(button, index) in navItems" :key="index" class="nav-button">
            <NavButton :button />
        </button>
    </div>
</template>

<script setup>
import NavButton from './NavButton.vue';


const navItems = [
  { name: '', link: '/', frame: 'nav-home' },
  { name: 'Rules', link: '/', frame: 'blue' },
  { name: 'Legal Cards', link: '/cards', frame: 'black' },
  { name: 'Decks', link: '/decks', frame: 'red' },
  { name: 'About', link: '/guides', frame: 'green' }
];

</script>

<style scoped>

.gradient-box {
    padding: 20px;
    background: linear-gradient(to bottom, rgb(0, 0, 0), rgba(0, 0, 0, 0));
    display: flex;
    justify-content: center;
    margin-top: 0px;
}

.nav-button {
    background-color: transparent;
    border: none;
    color: white;
    font-size: 18px;
    margin: 0 10px;
    cursor: pointer;
    
}

</style>
