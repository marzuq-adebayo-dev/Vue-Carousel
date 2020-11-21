# Examples

## Basic Example

```vue
<template>
  <carousel :items-to-show="1.5" :wrap-around="true">
    <slide v-for="slide in 10" :key="slide">{{ slide }}</slide>

    <template #addons>
      <navigation />
      <pagination />
    </template>
  </carousel>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Pagination, Navigation, Slide } from 'vue3-carousel';

export default {
  name: 'App',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
};
</script>
```

## Breakpoints

```vue
<template>
  <carousel :settings="settings" :breakpoints="breakpoints">
    <slide v-for="slide in 10" :key="slide">{{ slide }}</slide>

    <template #addons>
      <navigation />
      <pagination />
    </template>
  </carousel>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Pagination, Navigation, Slide } from 'vue3-carousel';

export default {
  name: 'App',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data: () => ({
    // carousel settings
    settings: {
      itemsToShow: 1.5,
      wrapAround: true,
      snapAlign: 'center',
    },
    // breakpoints are mobile first
    // any settings not specified will fallback to the carousel settings
    breakpoints: {
      // 700px and up
      700: {
        itemsToShow: 3.5,
        snapAlign: 'start',
      },
      // 1024 and up
      1024: {
        itemsToShow: 5,
        wrapAround: false,
        snapAlign: 'start',
      },
    },
  }),
};
</script>
```