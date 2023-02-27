<template>
  <div class="relative h-screen flex justify-center items-center bg-gray-100">
    <button class="px-4 py-2 bg-blue-600 rounded-md text-white mr-2" @click="toast.add({ message: 'Toast message!' })">Add toast</button>
    <button class="px-4 py-2 bg-blue-600 rounded-md text-white" @click="showAlert ^= true">Show Alert</button>

    <Toast />

    <div class="absolute top-4 right-4 space-y-4">
      <Alert
        :show="!!showAlert"
        :on-dismiss="() => (showAlert = false)"
        title="This is my awesome alert!"
        class="max-w-md w-full"
      />
      <Alert
        intent="success"
        :show="!!showAlert"
        :on-dismiss="() => (showAlert = false)"
        title="This is my awesome alert!"
        class="max-w-md w-full"
      />
      <Alert
        intent="warning"
        :show="!!showAlert"
        :on-dismiss="() => (showAlert = false)"
        title="This is my awesome alert!"
        class="max-w-md w-full"
      />
      <Alert
        intent="danger"
        :show="!!showAlert"
        :on-dismiss="() => (showAlert = false)"
        title="This is my awesome alert!"
        class="max-w-md w-full"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Alert from '@/components/Alert.vue'
import Toast from '@/components/Toast.vue'
import toast from '@/store/toast'

const showAlert = ref(false)
</script>
