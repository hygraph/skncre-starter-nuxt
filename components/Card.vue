<script setup>
defineProps(["image", "title", "url", "cta"]);
</script>
<template>
  <div class="bg-tertiary aspect-[1/1] relative">
    <a class="block absolute w-full h-full top-0 left-0" :href="url">
      <img
        v-if="image && image.url"
        :src="image.url"
        :alt="image.alt || title"
        width="500"
        height="500"
        class="absolute w-100 h-auto"
        loading="lazy"
      />

      <img
        v-else
        :src="image"
        :alt="title"
        class="absolute w-100 h-auto"
        loading="lazy"
        width="500"
        height="500"
      />

      <button class="cta absolute bottom-4 right-4">{{ cta }}</button>
      <div class="absolute top-6 md:top-auto md:-bottom-6 left-8">
        <h3>
          <span
            class="block text-primary font-bold font-title text-4xl md:text-6xl"
            >your</span
          ><span
            class="block text-dark font-bold font-title text-3xl sm:text-4xl md:text-6xl sm:ml-8 sm:-mt-2"
            >{{ title }}</span
          >
        </h3>
      </div></a
    >
  </div>
</template>
