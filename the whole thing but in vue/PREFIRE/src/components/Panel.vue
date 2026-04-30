<template>
    <div 
        class="panel"
        :class="{ 'image': image }"
        :style="{
            ...imageStyle,
            textAlign: centerText ? 'center' : undefined
        }"
    >
        <div class="header">{{ title }}</div>
        <slot 
            :style="{textAlign: centerText ? 'center' : ''}"
            style="text-align: center"
        ></slot>
    </div>

</template>

<script setup> 
import { computed } from 'vue';

const props = defineProps({
    title: String,
    image: Image,
    centerText: Boolean
})

const imageStyle = computed(() => {
  if (!props.image) return {};

  return {
    backgroundImage: `url(${props.image})`,
    backgroundSize: 'cover',
    backgroundPosition: 'center',
    backgroundRepeat: 'no-repeat'
  };
});
</script>

<style scoped>
.header {
  font-size: 1.5em;
  font-weight: bold;
  padding: 10px;
  border          : 5px solid var(--col-dark-1);
  background-image: linear-gradient(var(--col-dark-1), var(--col-dark-2));
  font-family: Beleren;
  text-align: center;
}

.panel {
  --border-width  : 5px;
  animation       : 0.5s forwards fadein linear;
  width           : calc(80% - calc(var(--border-width) * 2)); margin-inline: 10%;
  margin-block    : 20px;
  padding-bottom  : 55px;
  border          : 5px solid var(--col-darker);
  border-radius   : 2px 2px 10% 10%;
  box-shadow      : 0px 0px 1px 2px inset var(--col-dark-1), 0px 2px 8px 2px var(--col-dark-1);
  color          : var(--col-lightest);
}

.panel:not(.image) {
  background-image: linear-gradient(var(--col-dark-1-transparent), var(--col-dark-2-transparent));
}

.image {
  background-size: cover;
  background-position: center;
  max-height: 200px;
}
</style>
