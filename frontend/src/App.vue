<script setup lang="ts">
import { Button, Card } from 'primevue'
import { ref } from 'vue'
import WelcomeView from './components/WelcomeView.vue'
import AddressView from './components/AddressView.vue'
import OptionsView from './components/OptionsView.vue'
import SummaryView from './components/SummaryView.vue'

enum PAGE {
  WELCOME = 0,
  ADDRESS = 1,
  OPTIONS = 2,
  SUMMARY = 3,
}

const pages = {
  [PAGE.WELCOME]: WelcomeView,
  [PAGE.ADDRESS]: AddressView,
  [PAGE.OPTIONS]: OptionsView,
  [PAGE.SUMMARY]: SummaryView,
}

const currentPage = ref(PAGE.WELCOME)

function next() {
  currentPage.value = currentPage.value + 1
}

function prev() {
  currentPage.value = currentPage.value - 1
}
</script>

<template>
  <div class="flex justify-center md:mt-40">
    <Card class="md:w-150 w-full h-[100vh] md:h-auto flex flex-col">
      <template #header>
        <div class="w-full h-52 bg-primary flex text-white items-center justify-center">
          <i class="pi pi-trash text-9xl!" />
        </div>
      </template>
      <template #title>Waste Calendar - Ihr persönlicher Abfallkalender</template>
      <template #subtitle v-if="currentPage > 0">
        Schritt {{ currentPage }} von {{ PAGE.SUMMARY }}</template
      >
      <template #content>
        <div class="flex-1 overflow-auto">
          <component :is="pages[currentPage]" />
        </div>
      </template>
      <template #footer>
        <Button @click="next" v-if="currentPage === PAGE.WELCOME" class="mt-4 mx-auto w-full">
          Los geht's!
        </Button>
        <div v-else class="flex gap-4 justify-center mt-1">
          <Button @click="prev" class="w-full" severity="secondary" variant="outlined"
            >Zurück</Button
          >
          <Button @click="next" class="w-full">Weiter</Button>
        </div>
      </template>
    </Card>
  </div>
</template>

<style scoped lang="css">
:deep(.p-card .p-card-body),
:deep(.p-card .p-card-body .p-card-content) {
  @apply h-full flex flex-col;
}
</style>
