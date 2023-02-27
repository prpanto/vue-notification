<template>
  <TransitionGroup 
    tag="div"
    enter-from-class="translate-x-full opacity-0"
    enter-active-class="duration-500"
    leave-active-class="duration-500"
    leave-to-class="translate-x-full opacity-0"
    class="fixed top-4 right-4 z-50 w-full max-w-xs space-y-4"
  >
    <ToastListItem
      v-for="(item, index) in toast.items"
      :key="item.key"
      :message="item.message"
      @remove="remove(index)"
    />
  </TransitionGroup>
</template>

<script setup>
import { onUnmounted } from 'vue'
import ToastListItem from '@/components/ToastItem.vue'
import toast from '@/store/toast'

const removeFinishEventListener = () => toast.add({ message: 'Toast message!' })
const remove = index => toast.remove(index)

onUnmounted(() => removeFinishEventListener())
</script>
