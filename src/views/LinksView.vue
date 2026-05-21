<script setup lang="ts">
import { computed } from 'vue'
import { useTheme } from 'vuetify'
import LinkButton from '@/components/LinkButton.vue'

const theme = useTheme()
const isDark = computed(() => theme.global.name.value === 'dark')

function toggleTheme() {
  theme.global.name.value = isDark.value ? 'light' : 'dark'
}

const links = [
  { label: 'Portfolio', url: 'https://example.com', icon: 'mdi-briefcase-variant' },
  { label: 'Dribbble', url: 'https://dribbble.com', icon: 'mdi-dribbble' },
  { label: 'LinkedIn', url: 'https://linkedin.com', icon: 'mdi-linkedin' },
  { label: 'Email', url: 'mailto:hello@example.com', icon: 'mdi-email' },
]
</script>

<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-row justify="center" align="center" no-gutters class="w-100">
        <v-col cols="12" sm="8" md="6" lg="4" style="max-width: 480px">
          <v-card class="pa-6 text-center" rounded="lg" elevation="6">
            <div class="d-flex justify-end mb-n4">
              <v-btn
                :icon="isDark ? 'mdi-weather-sunny' : 'mdi-weather-night'"
                variant="text"
                size="small"
                :aria-label="isDark ? 'Switch to light theme' : 'Switch to dark theme'"
                @click="toggleTheme"
              />
            </div>

            <v-avatar size="96" color="primary" class="mb-4">
              <v-icon size="56" icon="mdi-account" />
            </v-avatar>

            <h1 class="text-h5 font-weight-bold mb-1">Brooke Jackson</h1>
            <p class="text-body-2 text-medium-emphasis mb-6">
              Designer · Developer · Adventurer of the Valley
            </p>

            <div class="d-flex flex-column ga-3">
              <LinkButton
                v-for="link in links"
                :key="link.label"
                :label="link.label"
                :url="link.url"
                :icon="link.icon"
              />
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
