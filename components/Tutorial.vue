<script setup>
import { getComponentForName } from "./componentMapper";
defineProps(["image", "title", "items"]);
</script>

<template>
  <section class="relative">
    <img
      :src="image.url"
      class="absolute h-full w-full object-cover"
      width="2880"
      height="1956"
      :alt="title"
      loading="lazy"
    />

    <div class="max-w-2xl px-12 py-24 md:px-24 md:py-36 relative">
      <h1 class="text-6xl font-bold mb-12 text-primary">{{ title }}</h1>

      <ul>
        <component
          v-for="(component, index) in items"
          :is="getComponentForName(component?.__typename)"
          :key="component?.id"
          v-bind="component"
          :index="index"
        />
      </ul>
    </div>
  </section>
</template>
