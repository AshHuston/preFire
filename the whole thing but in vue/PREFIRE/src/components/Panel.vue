<template>
    <div 
        class="panel"
        :style="{
            ...imageStyle,
            textAlign: centerText ? 'center' : undefined
        }"
    >
        <div class="header" :style="{textAlign: centerTitle ? 'center' : ''}">{{ title }}</div>
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
    image: String,
    centerText: Boolean,
    centerTitle: Boolean
})

const imageStyle = computed(() => {
  const base = {
    backgroundSize: 'cover',
    backgroundPosition: 'center',
    backgroundRepeat: 'no-repeat'
  };

  if (!props.image) {
    return {
      ...base,
      backgroundImage: `linear-gradient(
        var(--col-dark-1-transparent),
        var(--col-dark-2-transparent)
      )`
    };
  }

  return {
    ...base,
    backgroundImage: `
      linear-gradient(
        to right,
        var(--col-dark-1-transparent),
        #00000077
      ),
      url(${props.image})
    `
  };
});
</script>

<style scoped>
.header {
  font-size: 1.5em;
  font-weight: bold;
  padding: 5px;
  border          : 5px solid var(--col-dark-1);
  background-image: linear-gradient(var(--col-dark-1), var(--col-dark-2));
  font-family: Beleren;
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
  color           : var(--col-lightest);
}
</style>
