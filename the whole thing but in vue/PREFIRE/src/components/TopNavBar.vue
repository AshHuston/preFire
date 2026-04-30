<template>
    <div class="gradient-box">
        <NavButton 
            v-for="(button, index) in filteredNavItems" 
            :key="index" 
            class="nav-button" 
            :button
        />
    </div>
</template>

<script setup>
import NavButton from './NavButton.vue';
import { computed } from 'vue';

const props = defineProps({
    navItems: {
        type: Array,
        required: true
    }
});

const filteredNavItems = computed(() =>
    props.navItems.filter(b => b.frame !== 'discord')
);

</script>

<style scoped>

.gradient-box {
    padding: 0px;
    background: linear-gradient(to bottom, rgb(0, 0, 0), rgba(0, 0, 0, 0));
    display: flex;
    justify-content: center;
    align-items: center;
}

/* .nav-button {
    background-color: transparent;
    border: none;
    color: white;
    font-size: 18px;
    margin: 0 10px;
    cursor: pointer;
    width: 250px;
} */

</style>
