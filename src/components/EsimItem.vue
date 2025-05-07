<template>
  <div class="plan-item" :class="{ active: selected }" @click="$emit('select')">
    <div class="plan-info">
      <div class="data">
        <strong>{{ plan.dataVolume }}</strong>
        <span>{{ plan.esimDuration }}</span>
      </div>
      <div class="vpn">
        <strong>{{ plan.vpnVolume }}</strong>
        <span>{{ plan.vpnDuration }}</span>
      </div>
    </div>

    <div class="plan-price">
      <div v-if="plan.discount" class="discount">−{{ plan.discount }}%</div>
      <div  class=""></div>
      <div>
        <strong :class="['final-price',{'final-price-discount':plan.discount}]">${{ plan.finalPrice.toFixed(2) }}</strong>
        <span v-if="plan.discount" class="original-price">${{ plan.originalPrice.toFixed(2) }}</span>
      </div>
      <div class="radio">
        <span :class="{ selected }"></span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  plan: Object,
  selected: Boolean
})
defineEmits(['select'])
</script>

<style scoped lang="scss">
</style>
