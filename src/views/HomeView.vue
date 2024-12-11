<template>
  <div class="route-main">
    <h1>{{ pageTitle }}</h1>
    <MainComponent />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import MainComponent from '@/components/MainComponent.vue'

export default defineComponent({
  name: 'HomeView',
  components: {
    MainComponent,
  },
  setup() {
    const route = useRoute()
    const pageTitle = ref<string | symbol | null | undefined>(null)

    onMounted(() => {
      pageTitle.value = route.name
    })

    return {
      pageTitle,
    }
  },
})
</script>
