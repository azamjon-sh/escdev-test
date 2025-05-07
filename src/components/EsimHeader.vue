<script setup>

import EsimButton from "@/components/EsimButton.vue";
</script>

<template>
<header class="esim__header">
  <div class="container">
    <div class="esim__header__grid">
      <img src="@/assets/images/logo.svg" alt="Logo" class="esim__header__logo">
      <div class="esim__header__right">
        <div class="esim__header__help">
          <img src="@/assets/images/help.svg" alt="Help">
          Help
        </div>
        <EsimButton>Get started</EsimButton>
      </div>
    </div>
  </div>
</header>
</template>

<style scoped>

</style>