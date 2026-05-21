<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener"
    :prepend-icon="icon"
    color="primary"
    size="large"
    block
  >
    {{ label }}
  </v-btn>
</template>
