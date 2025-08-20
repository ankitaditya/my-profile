<script setup lang="ts">
import { Icon } from '@iconify/vue'
defineProps<{
  title: string
  icon: string
  open: boolean
}>()
const emit = defineEmits(['toggle'])
</script>

<template>
  <div class="section-card" :class="{ open }">
    <div class="section-header" @click="emit('toggle')">
      <Icon :icon="icon" class="section-icon" />
      <h2>{{ title }}</h2>
      <button
        class="toggle-btn"
        :aria-label="open ? 'Collapse section' : 'Expand section'"
        :aria-expanded="open"
      >
        <Icon :icon="open ? 'mdi:chevron-up' : 'mdi:chevron-down'" />
      </button>
    </div>
    <transition name="fade-slide">
      <div v-show="open" class="section-content">
        <slot />
      </div>
    </transition>
  </div>
</template>

<style scoped>
.section-card {
  background: #262626;
  border-radius: 24px;
  margin: 32px 0;
  box-shadow: 0 2px 16px 0 #9e7fff22;
  overflow: hidden;
  transition: box-shadow 0.2s;
}
.section-card.open {
  box-shadow: 0 4px 32px 0 #9e7fff44;
}
.section-header {
  display: flex;
  align-items: center;
  gap: 1em;
  padding: 1.5em 2em;
  cursor: pointer;
  user-select: none;
  background: linear-gradient(90deg, #171717 80%, #9e7fff22 100%);
  border-bottom: 1px solid #2f2f2f;
}
.section-icon {
  font-size: 2rem;
  color: #9e7fff;
}
h2 {
  flex: 1;
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0;
  color: #fff;
}
.toggle-btn {
  background: none;
  border: none;
  color: #a3a3a3;
  font-size: 1.5rem;
  cursor: pointer;
  transition: color 0.2s;
  border-radius: 50%;
  padding: 0.25em;
}
.toggle-btn:focus {
  outline: 2px solid #9e7fff;
  color: #9e7fff;
}
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 0.4s cubic-bezier(.4,0,.2,1);
}
.fade-slide-enter-from,
.fade-slide-leave-to {
  opacity: 0;
  transform: translateY(24px);
}
.section-content {
  padding: 2em;
  color: #fff;
  font-size: 1.1rem;
}
@media (max-width: 600px) {
  .section-header {
    padding: 1em 1em;
  }
  .section-content {
    padding: 1em;
  }
}
</style>
