<template>
    <div class="navbar">
        <a 
            v-for="(button, index) in navItems" 
            :key="index" 
            class="nav-button"
            :href="button.link"
        >
            <div v-if="button.frame === 'discord'">
                <img 
                    class="discord-svg"
                    src="../RESOURCES/img/discord.svg"
                />
            </div>
            <div v-else-if="button.frame === 'nav-home'">
                <img 
                    class="icon"
                />
            </div>
            <div v-else>
                {{ button.name }}
            </div>
        </a>
    </div>
</template>

<script setup>

defineProps({
    navItems: {
        type: Array,
        required: true
    }
});

</script>

<style scoped>

.navbar {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: black;
    color: white;
    margin: 0px;

    & :first-child {
        margin-left: 5%;
        margin-right: -5%;
    }
    & :last-child {
        margin-left: -5%;
        margin-right: -5%;
    }   
}

.nav-button {
    background-color: transparent;
    text-decoration: none;
    font-family: Beleren;
    font-size: large;
    color: #555555;
    cursor: pointer;
    flex: 1;
    margin: 5px;

    &:hover{
        color       : white;
        z-index     : 2;
        transition  : 0.2s;
        cursor      : pointer;
    }
}   
.discord-svg {
    width: 125px;
    border-radius: 25px;
}

.icon {
  width: 50px;
  height: 50px;
  background-color: #555555;

  -webkit-mask-image: url("../RESOURCES/img/ui/home.png");
  -webkit-mask-repeat: no-repeat;
  -webkit-mask-size: contain;

  mask-image: url("../RESOURCES/img/ui/home.png");
  mask-repeat: no-repeat;
  mask-size: contain;

  &:hover{
    background-color       : white;
    z-index     : 2;
    transition  : 0.2s;
    cursor      : pointer;
  }
}

</style>
