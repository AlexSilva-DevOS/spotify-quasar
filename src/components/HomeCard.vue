<template>
  <q-card class="bg-dark text-white rounded--md cursor-pointer hover:scale-[1.03] transition-transform"
    style="max-width: 180px; width: 100%" @Click="goToLibrary">

    <q-img :src="image" ratio="1" class="rounded-md" />

    <q-card-section class="q-pa-sm">
      <div class="text-body1 ellipsis">{{ title }}</div>
      <div class="text-grey-6 text-caption ellipsis">{{ subTitle }}</div>
    </q-card-section>
  </q-card>
</template>

<script setup>

import { toRefs } from 'vue'
import { useRouter } from 'vue-router'

const props = defineProps({
  image: String,
  title: String,
  subTitle: String,
})

const { image, title, subTitle } = toRefs(props)
const router = useRouter()

const goToLibrary = () => {
  router.push('/library')
}

</script>
