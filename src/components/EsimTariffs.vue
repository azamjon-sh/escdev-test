<script setup>
import {ref} from 'vue'
import PlanItem from './EsimItem.vue'
import EsimButton from "@/components/EsimButton.vue";

const selected = ref(0)

const plans = [
  {
    dataVolume: '500 MB',
    vpnVolume: '∞ GB',
    esimDuration: '7 days eSIM',
    vpnDuration: '7 days VPN',
    originalPrice: 10,
    finalPrice: 10
  },
  {
    dataVolume: '1 GB',
    vpnVolume: '∞ GB',
    esimDuration: '30 days eSIM',
    vpnDuration: '30 days VPN',
    originalPrice: 20,
    finalPrice: 20
  },
  {
    dataVolume: '3 GB',
    vpnVolume: '∞ GB',
    esimDuration: '30 days eSIM',
    vpnDuration: '30 days VPN',
    originalPrice: 30,
    finalPrice: 30
  },
  {
    dataVolume: '5 GB',
    vpnVolume: '∞ GB',
    esimDuration: '7 days eSIM',
    vpnDuration: '6 months VPN',
    originalPrice: 50,
    finalPrice: 42.12,
    discount: 50
  },
  {
    dataVolume: '10 GB',
    vpnVolume: '∞ GB',
    esimDuration: '60 days eSIM',
    vpnDuration: '6 months VPN',
    originalPrice: 60,
    finalPrice: 51.03,
    discount: 50
  },
  {
    dataVolume: '20 GB',
    vpnVolume: '∞ GB',
    esimDuration: '60 days eSIM',
    vpnDuration: '1 year VPN',
    originalPrice: 80,
    finalPrice: 80
  }
]
</script>
<template>
  <div class="plan-list">
    <PlanItem
        v-for="(plan, index) in plans"
        :key="index"
        :plan="plan"
        :selected="index === selected"
        @select="selected = index"
    />
  </div>
  <EsimButton size="large">Buy now</EsimButton>
  <p class="plan-guaranty">
    <img src="@/assets/images/shield.svg" alt="">
    Secure payment guaranteed.

  </p>
</template>


