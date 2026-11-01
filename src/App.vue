<script setup lang="ts">
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { RouterLink, RouterView } from 'vue-router'
import { useDeliveryStore } from './store'
const store = useDeliveryStore()
const { approvedShare, offers, urgent } = storeToRefs(store)
onMounted(store.load)
</script>

<template><div class="shell"><aside><div class="brand">BuildProductEU<span>CPR TRANSITION</span></div><nav><RouterLink to="/">Construction product reviews</RouterLink><RouterLink to="/insights">Transition guidance</RouterLink></nav><div class="health"><i /> Java construction product transition service connected</div></aside><main><header><div><span class="eyebrow">Accelerate safer and more sustainable construction products through digital product information</span><h1>Construction Product Transition Desk</h1></div><button @click="store.addOffer">Add construction product review</button></header><section class="summary"><article><small>Products ready</small><strong>{{ approvedShare }}%</strong><div class="bar"><span :style="{ width: `${approvedShare}%` }" /></div></article><article><small>Construction product reviews tracked</small><strong>{{ offers.length }}</strong><p>Shared transition view</p></article><article><small>High-priority gaps</small><strong>{{ urgent }}</strong><p>Needs attention</p></article></section><RouterView /></main></div></template>
