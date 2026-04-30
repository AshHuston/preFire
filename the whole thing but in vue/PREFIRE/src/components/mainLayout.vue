<template>
  <div class="mainLayout background_splinter_twin">
    <header class="header"><h1>PreFIRE</h1></header>
    <TopNavBar />
    <slot>
        <p>Error loading page info...</p>
    </slot>
    <!-- <BottomNavBar /> -->
  </div>
</template>

<script setup>
import TopNavBar from './TopNavBar.vue';
// import BottomNavBar from './BottomNavBar.vue';
</script>

<style scoped>

h1 {
  margin-bottom: 0;
}

.mainLayout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.header {
  text-align: center;
  color: #555555;
  background-color: black;
}

.background_splinter_twin{
  background-image      : url("../RESOURCES/img/backgrounds/splinter_twin.webp");
  background-size       : cover;
  background-repeat     : no-repeat;
  background-position   : center;
}

</style>
