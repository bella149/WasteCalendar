<script setup lang="ts">
import { ref } from 'vue'
import MultiSelect from 'primevue/multiselect'

const selectedCities = ref<string[]>([])
const groupedCities = ref([
  {
    label: 'Sonstige Gemeinden',
    code: 'SONSTIGE_GEMEINDEN',
    items: [
      { label: 'Bellenberg', value: 'BELLENBERG' },
      { label: 'Altenstadt', value: 'ALTENSTADT' },
      { label: 'Holzheim', value: 'HOLZHEIM' },
      { label: 'Kellmünz', value: 'KELLMUENZ' },
      { label: 'Nersingen', value: 'NERSINGEN' },
      { label: 'Oberroth', value: 'OBERROTH' },
      { label: 'Osterberg', value: 'OSTERBERG' },
      { label: 'Roggenburg', value: 'ROGGENBURG' },
      { label: 'Unterroth', value: 'UNTERROTH' },
    ],
  },
  {
    label: 'Buch',
    code: 'BUCH',
    items: [
      { label: 'Gannertshofen', value: 'GANNERTSHOFEN' },
      { label: 'Buch (weitere)', value: 'BUCH_WEITERE' },
    ],
  },
  {
    label: 'Elchingen',
    code: 'ELCHINGEN',
    items: [
      { label: 'Thalfingen', value: 'THALFINGEN' },
      { label: 'Ober-Unter', value: 'OBER_UNTER' },
    ],
  },
  {
    label: 'Illertissen',
    code: 'ILLERTISSEN',
    items: [
      { label: 'Tiefenbach', value: 'TIEFENBACH' },
      { label: 'Betlinshausen', value: 'BETLINSHAUSEN' },
      { label: 'Illertissen OST', value: 'ILLERTISSEN_OST' },
      { label: 'Au', value: 'AU' },
      { label: 'Jedesheim', value: 'JEDESHEIM' },
      { label: 'Illertissen WEST', value: 'ILLERTISSEN_WEST' },
    ],
  },
  {
    label: 'Neu-Ulm',
    code: 'NEU_ULM',
    items: [
      { label: 'Bezirk 01 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_01' },
      { label: 'Bezirk 02 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_02' },
      { label: 'Bezirk 03 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_03' },
      { label: 'Bezirk 04 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_04' },
      { label: 'Bezirk 05 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_05' },
      { label: 'Bezirk 06 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_06' },
      { label: 'Bezirk 07 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_07' },
      { label: 'Bezirk 08 (Neu-Ulm)', value: 'NEU_ULM_BEZIRK_08' },
    ],
  },
  {
    label: 'Pfaffenhofen',
    code: 'PFAFFENHOFEN',
    items: [
      { label: 'Pfaffenhofen', value: 'PFAFFENHOFEN' },
      { label: 'Biberberg', value: 'BIBERBERG' },
      { label: 'Diepertshofen', value: 'DIEPERTSHOFEN' },
      { label: 'Erbishofen', value: 'ERBISHOFEN' },
      { label: 'Niederhausen', value: 'NIEDERHAUSEN' },
      { label: 'Volkertshofen', value: 'VOLKERTSHOFEN' },
      { label: 'Balmertshofen', value: 'BALMERTSHOFEN' },
      { label: 'Berg Beuren', value: 'BERG_BEUREN' },
      { label: 'Hirbishofen', value: 'HIRBISHOFEN' },
      { label: 'Kadeltshofen', value: 'KADELTSHOFEN' },
      { label: 'Luippen', value: 'LUIPPEN' },
      { label: 'Raunertshofen', value: 'RAUNERTSHOFEN' },
      { label: 'Remmeltshofen', value: 'REMMELTSHOFEN' },
      { label: 'Roth', value: 'ROTH' },
    ],
  },
  {
    label: 'Senden',
    code: 'SENDEN',
    items: [
      { label: 'Bezirk 01 (Senden)', value: 'SENDEN_BEZIRK_01' },
      { label: 'Bezirk 02 (Senden)', value: 'SENDEN_BEZIRK_02' },
      { label: 'Bezirk 03 (Senden)', value: 'SENDEN_BEZIRK_03' },
      { label: 'Bezirk 04 (Senden)', value: 'SENDEN_BEZIRK_04' },
      { label: 'Bezirk 05 (Senden)', value: 'SENDEN_BEZIRK_05' },
      { label: 'Bezirk 06 (Senden)', value: 'SENDEN_BEZIRK_06' },
      { label: 'Bezirk 07 (Senden)', value: 'SENDEN_BEZIRK_07' },
      { label: 'Bezirk 08 (Senden)', value: 'SENDEN_BEZIRK_08' },
      { label: 'Bezirk 09 (Senden)', value: 'SENDEN_BEZIRK_09' },
      { label: 'Bezirk 10 (Senden)', value: 'SENDEN_BEZIRK_10' },
      { label: 'Bezirk 11 (Senden)', value: 'SENDEN_BEZIRK_11' },
      { label: 'Bezirk 12 (Senden)', value: 'SENDEN_BEZIRK_12' },
    ],
  },
  {
    label: 'Vöhringen',
    code: 'VOEHRINGEN',
    items: [
      { label: 'Ost', value: 'OST' },
      { label: 'West', value: 'WEST' },
      { label: 'Illerberg', value: 'ILLERBERG' },
      { label: 'Illerzell', value: 'ILLERZELL' },
    ],
  },
  {
    label: 'Weißenhorn',
    code: 'WEISSENHORN',
    items: [
      { label: 'Emershofen', value: 'EMERSHOFEN' },
      { label: 'Ost', value: 'OST' },
      { label: 'West', value: 'WEST' },
      { label: 'Weitere', value: 'WEITERE' },
      { label: 'Grafertshofen', value: 'GRAFERTSHOFEN' },
      { label: 'Ober-/Wallenhausen', value: 'OBER_WALLENHAUSEN' },
      { label: 'Atten-/Hegelhofen', value: 'ATTEN_HEGELHOFEN' },
    ],
  },
])
</script>

<template>
  <div>
    <p class="font-bold">Für welche Orte möchten Sie den Abfallkalender abrufen?</p>
    <div class="mt-2 mb-4">
      <MultiSelect
        v-model="selectedCities"
        :options="groupedCities"
        optionLabel="label"
        filter
        optionGroupLabel="label"
        optionGroupChildren="items"
        display="chip"
        placeholder="Orte auswählen"
        class="w-full"
      />
    </div>
  </div>
</template>
