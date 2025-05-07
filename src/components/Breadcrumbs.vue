<script setup>
import {ref} from "vue";

const links = ref([
  {link: "/", name: "Home"},
  {link: "/", name: "Region"},
  {link: "/", name: "Europe"},
])
</script>

<template>
  <div class="breadcrumbs">
    <a class="breadcrumbs__link" :href="item.link" v-for="(item,i) in links">
      {{ item.name }}
      <span>{{ i + 1 !== links.length ? '/' : '' }}</span></a>
  </div>
</template>

<style scoped>

</style>