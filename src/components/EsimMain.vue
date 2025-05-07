<script setup>

import Breadcrumbs from "@/components/Breadcrumbs.vue";
import EsimButton from "@/components/EsimButton.vue";
import EsimTariffs from "@/components/EsimTariffs.vue";
</script>

<template>
  <main class="esim__main">
    <div class="container">
      <Breadcrumbs/>
      <div class="esim__grid">
        <div class="esim__image">
          <img src="@/assets/images/image.png" alt="">
        </div>
        <div class="esim__right">
          <h1 class="esim__title">
            <img src="@/assets/images/excdev.svg" alt="">
            eSIM Europe + VPN
          </h1>
          <div class="esim__buttons">
            <EsimButton color="white">Features</EsimButton>
            <EsimButton color="outline">Tech specs</EsimButton>
          </div>
          <ul class="esim__list">
            <li class="esim__list__item">
              33 countries
            </li>
            <li class="esim__list__item">
              Reliable connection from best networks.
            </li>
            <li class="esim__list__item">
              You will only get mobile data and keep your original phone number.
            </li>
            <li class="esim__list__item">
              Works with all smartphones with eSIM technology.
            </li>
          </ul>
          <EsimTariffs/>
        </div>
      </div>
    </div>

  </main>


</template>