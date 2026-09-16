<template>
  <div class="accordion custom-accordion" id="faq">
    <div v-for="(item, i) in items" :key="item.q" class="accordion-item">
      <h2 class="accordion-header">
        <button
          class="accordion-button"
          :class="{ collapsed: openIndex !== i }"
          type="button"
          :aria-expanded="openIndex === i"
          :aria-controls="'q' + i"
          @click="toggle(i)"
        >
          <span>{{ item.q }}</span>
          <i class="bi" :class="openIndex === i ? 'bi-dash-lg' : 'bi-plus-lg'" aria-hidden="true"></i>
        </button>
      </h2>
      <div
        :id="'q' + i"
        class="accordion-collapse"
        :class="{ show: openIndex === i }"
        :aria-hidden="openIndex !== i"
      >
        <div class="accordion-body">{{ item.a }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({ items: { type: Array, default: () => [] } })
const openIndex = ref(-1)
const toggle = (index) => {
  openIndex.value = openIndex.value === index ? -1 : index
}
</script>
